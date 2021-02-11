You have the ability to provide a running Docker daemon for the user in case you need to allow them to build and run container images. Additionally, you may provide the user a temporary private container registray that they can use to push container to. These can be enabled in the `workshop.yaml` file:

```
spec:
  session:
    applications:
      docker:
        enabled: true
      registry:
        enabled: true
```

When enabled, several environment variables are made available which can be used to interact with this registry:

```terminal:execute
command: |+
  echo "REGISTRY_HOST: $REGISTRY_HOST
  REGISTRY_USERNAME: $REGISTRY_USERNAME
  REGISTRY_PASSWORD: $REGISTRY_PASSWORD
  REGISTRY_SECRET: $REGISTRY_SECRET
  REGISTRY_AUTH_FILE: $REGISTRY_AUTH_FILE"
```

These values are available within the workshop as well, just as other variables such as `workshop_name` are:

`registry_host` : {{ registry_host }}

`registry_username` : {{ registry_username }}

`registry_password`: {{ registry_password }}

`registry_secret`: {{ registry_secret }}

`registry_auth_file`: {{ registry_auth_file }}


You can use this information to build your lab and push it to the local registry:

```terminal:execute
command: |+ 
  cd ~/lab-learn-labs
  docker build . -t {{ registry_host }}/my-lab
```

```terminal:execute
command: docker push {{ registry_host }}/my-lab
```