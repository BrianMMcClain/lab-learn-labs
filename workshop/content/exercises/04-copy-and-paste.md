When writing an exercise for a workshop, you can copy text to the user's paste buffer as follows:

````
```workshop:copy
text: echo "Text to copy"
```
````

Give it a try yourself! Click the exemple below, then paste it in one of the terminals on the right:

```workshop:copy
text: echo "Text to copy"
```

You can also annotate the block to alert the user that they should edit the text after pasting it:

````
```workshop:copy-and-edit
text: echo "Text to copy and edit."
```
````

This changes the header a bit, as shown below:

```workshop:copy-and-edit
text: echo "Text to copy and edit."
```