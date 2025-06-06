## setup vim
```
edit the following file 
sudo vim /etc/vim/vimrc

set syntax
set number
set realtivenumber
set ruler

```

[comprehensive vim cheat sheet](https://vim.rtorr.com/)


## Cursor Motion Keys

| Navigation  | Description |  
| :----------: | :--------- | 
| h  | move cursor right |
| l  | move cursor left |
| j  | move cursor down |
| k  | move cursor up |
| ^  | begining of the line | 
| 0  | begining of the line | 
| $  | end of the line  |     
| B  | Previous Word  or , or . |      
| b  | Previous Word ignores , or .   |      
| w  | moves to beging of word or , or .  | 
| W  | moves to begining of word ignores punctuation |
| gg   | moves to top of document first line | 
| Shift g |  moves to the bottomo of the document | 
|  29gg  |  moves to line 29  |
|  29g  |   moves to line 29  | 
|    |                 | 
|    |                 | 
|    |                 | 
|    |                 | 
|    |                 | 
|    |                 | 
|    |                 | 


## Entering Text

| Command | Action |
| :---:  | :--- |
| i  | insert at the cursor |
| I  | insert at the beginning of the line |
| o  | insert below cursor new line |
| O  | insert above cursor new line |
| a  | append after the cursor |
| A  | append at the end of the line |



## Screen Navigation

| Navigation | Description |
| :---:| :--- |
| Ctrl - B | Page Back  |
| Ctrl - F | Page Forward  |
| Ctrl - U | Scroll Up  |
| Ctrl - D | Scroll Down  |
| z Enter  | Current line top of the screen  |
| z . | Current line middle of the screen  |
| z - | Current line bottom of the screen  |
| Ctrl - L |   |


## Deleting Text


| Command | Action |
| :---:  | :--- |
| x  | delete character | 
| X  | delete character before cursor |
| dW  | delete Word ignores punctuation |
| dw  | delete Word abides punctuation |
| 3dw | deletes next 3 words  [count]operation{motion}|
| 2d3w | deletes the 3w three words motion 2 times |
| dd  | delete line |
|  . | after you have used dd if you press . it will repeat the last command |
| dj  | delete line below cursor |
| dl  | delete line above cursor |
| d^  | begining line |
| d$  | end of line |
| D$  | delete to the end of the line |
| (   | beginning of the sentence  |
| )   | end of the sentence  |
| {   | beginning of the paragraph |
| }   | end of the paragraph  |


## Saving a file

| Command | Action |
| :---:  | :--- |
| :wq! | write and quit | 
|  :w | write (like saving document) |
| :q! | quit without saving |



## Getting Help


| Command | Action |
| :---:  | :--- |
| :help  | splits the screen into two panes | 
| :q | quits help |
| :help dd  | goes to the delete help section |
| ctrl - W | switch between help window and the editing window |
| :h :q[then press ctl d] | gives you a form of command complete all options of :q (hit tab key scroll trhu options) |

