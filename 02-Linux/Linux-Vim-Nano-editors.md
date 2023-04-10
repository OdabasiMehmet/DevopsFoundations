If you’re looking to work with text files on a Linux system, you have two options to choose from: Vim and Nano. Both of these text editors are powerful, versatile, and widely used by developers and system administrators alike.

Vim, which stands for Vi IMproved, is a highly configurable and feature-rich text editor that has been around for over two decades. Despite its reputation for being difficult to use at first, Vim has a large and dedicated following who love it for its speed and efficiency once you get the hang of it.

Nano, on the other hand, is a more beginner-friendly text editor that is often used as a simple, straightforward alternative to Vim. Nano has a user-friendly interface that makes it easy to get started with, and it’s a great choice if you’re just looking to make a few quick edits to a file.

# VIM EDITOR
Vim is a highly configurable and powerful text editor that has been around for over two decades. It is commonly used for editing configuration files, writing code, and performing other text-related tasks on Linux systems.

To get started with Vim, open a terminal window and type “vim” followed by the name of the file you want to edit. You can choose the name of an existing file, or a new file.

```bash
vim filename
```
## Normal (command) mode

Once in Vim, you will be in “normal mode,” which is used for navigation and commands. It is also called command mode.

## Insert mode

In normal mode, you cannot directly edit text, but instead, you must enter “insert mode” by pressing “i” to start typing.

## Save and exit

Add text and when you are finished, you need to go back to the normal mode to be able to save and exit the editor. To go back to the normal mode, hit escape (esc) button on your keyboard. Then enter colon followed by wq (write and quit) and hit enter to save and exit the application.

## Insert a new line

As I mentioned earlier, you need to press i to enter insert mode. There is another option to enter insert mode. The “o” command in Vim is used to insert a new line below the current line and enter insert mode. This allows you to add new text to the file without having to move the cursor to a new line first.
The “O” command is similar to “o”, but it inserts a new line above the current line instead of below it.

## Exit without saving

Let’s say, we did not modify the file and we just want to exit the editor. We can do that with the combination of esc followed by :q which is just quit. However, if you made some modifications but want to exit without saving, just entering :q will not be enough. You will get a warning. You need to add ! after q to be able to exit without saving.

## Copying and cutting text to paste

1. To copy text in Vim, move the cursor to the start of the text you want to copy, then press “v” to enter visual mode.
2. Use the arrow keys to select the text you want to copy, then press “y” to copy it. If you want to cut the text, use the letter “d” instead of “y” to cut the text.
3. To paste the copied or cut text, move the cursor to the desired location and press “p”.

## Deleting

In Vim, you can delete text using the “d” command. There are several variations of the “d” command, depending on how much text you want to delete:

* To delete a single character, move the cursor to the character and press “x”.
* To delete a word, move the cursor to the start of the word and press “dw”.
* To delete a line, move the cursor to the line and press “dd”.
* To delete to the end of the line, move the cursor to the start of the text you want to delete and press “D”.
* To delete multiple lines, move the cursor to the first line and press “n dd”, where “n” is the number of lines you want to delete. For example, “3 dd” will delete three lines.

## Searching in Vim

In Vim, you can search for text in a file using the “/” command while in command mode. To search for a specific word or phrase, press “/” and then type the word or phrase you want to search for. Then press “Enter” to initiate the search. You can use the “n” key to move to the next occurrence of the word, and the “N” key to move to the previous occurrence.

# NANO EDITOR
Nano is a simple and easy-to-use text editor for the terminal in Linux. It’s a good choice for beginners or for when you need to make quick edits to a file without having to learn a complex text editor.

Just like vi, to get started with Nano, open a terminal window and type “nano” followed by the name of the file you want to edit. You can choose the name of an existing file, or a new file.

```bash
nano filename
```
Unlike vim, you can immediately start writing with nano editor.

## Copying text

To copy text in Nano, we have two options: using the mouse and using the keyboard.

1. Using the Mouse
In Nano, the easiest way to copy and paste is to use the mouse. Just like in windows, use your mouse to select the text. Then right click the mouse to copy the text. Then go to the point where you want to paste the text, right click and hit paste.

2. Using the Keyboard:

Move the cursor to the beginning of the text that you want to copy. Press Ctrl + 6 to see Mark Set option. Then use the arrow keys to highlight the text you want to copy. Then press “Alt” + “6”. The text will be saved to a buffer, and you can paste it elsewhere in the file by pressing “Ctrl” + “U”.

## Searching for text

To search for text in Nano, press “Ctrl” + “W”. A prompt will appear at the bottom of the screen, where you can enter the text you want to search for. To find the next occurrence of the text, press “Alt” + “W”.

## Undoing in Nano

You can undo changes by hitting “Alt” + “U”.

## Saving and exiting

To save changes to a file in Nano, press “Ctrl” + “O” and then hit enter. To exit afterwards press “Ctrl” + “x”.

## Exiting without saving

You can exit without saving by using the “Ctrl” + “x” option. If you have not modified the file, you will directly return to terminal. However, if you have modified the file but try to exit without saving, you will be asked to confirm. Just hit “N” to exit without saving.
