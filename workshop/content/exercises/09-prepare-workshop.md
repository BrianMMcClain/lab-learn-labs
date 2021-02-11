```terminal:execute
command: |+
  kubectl delete secret -n eduk8s $SESSION_NAME-pull
  kubectl create secret docker-registry $SESSION_NAME-pull --docker-server=$REGISTRY_HOST --docker-username=$REGISTRY_USERNAME --docker-password=$REGISTRY_PASSWORD -n eduk8s
```

```editor:append-lines-to-file
file: ~/lab-learn-labs/resources/profile.yaml
text: |
  apiVersion: training.eduk8s.io/v1alpha1
  kind: SystemProfile
  metadata:
    name: {{ session_namespace }}-profile
  spec:
    ingress:
      domain: {{ ingress_domain }}
    environment:
      secrets:
        pull:
        - {{ session_namespace }}-pull
```

```terminal:execute
command: kubectl apply -f ~/lab-learn-labs/resources/profile.yaml
```

```terminal:execute
command: |+
  sed resources/workshop.yaml -e "s/name: lab-learn-labs/name: $SESSION_NAME-lab/" -i
  sed resources/workshop.yaml -e "s/image: brianmmcclain\/lab-learn-labs:latest/image: $REGISTRY_HOST\/my-lab:latest/" -i
```

```terminal:execute
command: |+
  sed resources/training-portal.yaml -e "s/name: lab-learn-labs/name: $SESSION_NAME-lab/" -i
```

```editor:insert-value-into-yaml
file: ~/lab-learn-labs/resources/training-portal.yaml
path: spec
value:
  system:
    profile: {{ session_namespace }}-profile
```