# Interaction: alert, prompt, confirm

## alert

This one we’ve seen already. It shows a message and waits for the user to press “OK”.

## prompt

The function prompt accepts two arguments:

It shows a modal window with a text message, an input field for the visitor, and the buttons OK/Cancel.

`title`
The text to show the visitor.

`default`
An optional second parameter, the initial value for the input field.

If user press Close or hitting <kbd>ESC</kbd> in prompt window it returns null.

***In IE: always supply a default***

## confirm

Shows a message and waits for the user to press “OK” or “Cancel”. It returns `true` for OK and `false` for Cancel/<kbd>Esc</kbd>.

***

There are two limitations shared by all the methods above:

1. The exact location of the modal window is determined by the browser. Usually, it’s in the center.
2. The exact look of the window also depends on the browser. We can’t modify it.




