You can also send interrupts to the terminal! First, let's start a long running command:


```terminal:execute
command: sleep 36000
session: 1
```

You'll see the terminal is not yet able to take any input as it's in the middle of processing a command. In this case, it's a simple sleep command, but this could be an infinitely command such as `watch` or `kubectl get pods -w`. Since these commands only end when the user sends an interrupt, the terminal would otherwise be tied up forever. 

An interrupt can be sent to a terminal by sending the `<ctrl-c>` command:

````
```terminal:interrupt
session: 1
```
````

Give it a try yourself!

```terminal:interrupt
session: 1
```
