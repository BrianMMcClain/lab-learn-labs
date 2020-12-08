Your workshops can interact with the terminals on the right in a number of ways using a few special Markdown tags. Let's first start by taking a look at the options you have for executing commands.

There are four tags that you can use to allow the user to click on the code block and execute a command (or multiple commands) in a terminal:

- `execute`: Executes a command in terminal 1
- `execute-1`: Also executes a command in terminal 1
- `execute-2`: Executes a command in terminal 2
- `execute-all`: Executes a command in all terminals

Let's take a look and see them in action:

#### Execute in terminal 1 

If no session is defined, the command will be ran in the first terminal:

````
```terminal:execute
command: echo "Hello from terminal 1"
```
````

```terminal:execute
command: echo "Hello from terminal 1"
```

You can also define a specific termainal to run the command in with the `session` tag:

````
```terminal:execute
command: echo "Hello from terminal 1"
session: 1
```
````

```terminal:execute
command: echo "Hello from terminal 1"
session: 1
```


#### Execute in terminal 2

````
```terminal:execute
command: echo "Hello from terminal 2"
session: 2
```
````

```terminal:execute
command: echo "Hello from terminal 2"
session: 2
```

#### Execute in all terminals

If you wish to execute a command in all terminals, you can use the `terminal:execute-all` annotation:

````
```terminal:execute-all
command: echo "Hello from all terminals!"
```
````

```terminal:execute-all
command: echo "Hello from all terminals!"
```