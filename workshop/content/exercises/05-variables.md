There are a few variables available to you when writing your workshop:

`workshop_name`: {{ workshop_name }}

`session_namespace`: {{ session_namespace }}

`workshop_namespace:` {{ workshop_namespace }}

`training_portal`: {{ training_portal }}

`ingress_domain`: {{ ingress_domain }}

`ingress_protocol`: {{ ingress_protocol }}

You can also include these varriables in command blocks:

{% raw %}
```terminal:execute
command: echo "The workshop name is %workshop_name%"
session: 1
```
{% endraw %}

This will render the vairable name directly in the command block:

```terminal:execute
command: echo "The workshop name is %workshop_name%"
session: 1
```