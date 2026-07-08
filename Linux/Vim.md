# VIM

Source: https://vimschool.netlify.app/introduction/getting_help/

- VI Improvement, modal editor.
- Is a highly efficient, free and open-source command-line text editor widely used in Linux environments.
- Allows to edit config files, write scripts and manage code directly from the terminal without needing
a graphical user interface (GUI).

- ESC is important to constantly type to guarantee that it is in Normal Mode.

## Modes 

| Mode   | Function                                                                      |
| ------ | ----------------------------------------------------------------------------- |
| Normal | Do actions like copy, paste, find or replace. (Ex.: :w to save or :q to quit) |
| Visual | Use to select the text.                                                       |
| Insert | Edit the text                                                                 |
++ look at the bottom left of vim’s screen and you’ll see which mode is currently in use. You can see **INSERT** or **VISUAL** for the respective modes, or when you don’t see anything it means you are in **NORMAL/COMMAND** mode.

## Command mode 
  - : = use to define which commands that I want to use.
  - % = apply the command in all lines.
  - c = confirm replace of everything.
  - x = erase one character 
  - i (before) /a (after text) = insert
  - wq = save a file and exit

### motions
* w = word
* $ = end of the line

#### d operator
  - d{number}w = place the cursor in the beginning of the word to delete it. When it has no number just delete one words, if there is multiple words, then it deletes the number of words defined.
  - d$ = delete everything after the cursor.
  - d = delete operator
  - de = delete the end of the current world, including the last character.
  
* {number}w = move the cursor to move n numbers forward
* {number}e = move the cursor to move to the end of the n numbers forward
* 0 = to move to the start of the line.
* u = undo if it is in capital U, then it return to initial state.
* {number}dd = delete n rows (default 1).
* control + y is control + r.

* Combined dd (delete line, it goes to the VIM register), then if we use p, it past back. 
* r{letter of interest} = type the r and the letter that you want to replace it.

#### C operator

c  {number} motion 

* ce = change the operator, therefore we type ce and then change all the rest of the string with the string defined by us (aka. deletes the word and places you in Insert Mode).
* cc = deletes the line and replaces by another.
* c$ = deletes from the cursor until the end of the line. Then we can rewrite the sentence replacing only from the cursor until  the end, instead of the whole sentence. 
* 