---
layout: post
title: "Learn Emacs: Keyboard Macros"
categories: [learn-emacs]
---

An emacs keyboard macro is just a recording of user input into emacs, which means that most anything you can do in emacs can be recorded as a macro. Read that again. Pretty powerful.

Here's how it works. To start recording, type

    C-x (

and input the commands in your macro. Then type

    C-x )

to stop recording. Then type

    C-x e

to apply the macro once, or

    C-u 0 C-x e

to apply the macro until the bell rings or end of buffer is reached

Keep in mind that you must not ring the bell when defining a keyboard macro (by accident, or with C-g). If you do, you'll have to start all over defining your keyboard macro

Typically I use a keyboard macro when I have a file full of data that needs slight altering, for example a non-standard CSV-like file. I'll define a macro in terms of what needs changing on each line and then apply the macro for each line (until the end of the buffer).

### Further Reading

* [emacs wiki on keyboard macros](http://www.emacswiki.org/emacs/KeyboardMacros)
* [keyboard macros tricks](http://www.emacswiki.org/emacs/KeyboardMacrosTricks)
* [emacs manual entry on keyboard macros](http://www.gnu.org/s/libtool/manual/emacs/Keyboard-Macros.html)

