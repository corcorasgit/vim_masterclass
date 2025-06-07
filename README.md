# VIM_Masterclass
VM Masterclass course on Undemy

## notes on GIT
### setting up ssh keys

1. Generate SSH key on your local computer
```
ssh-keygen -t ed25519 -C "corcoras.git@protonmail.com"
```
2. Add ssh key to the ssh agent
```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```
3. Add your public key to Github
```
cat ~/.ssh/id_ed25519.pub

shaun@x1:~/study/vim_masterclass$ cat ~/.ssh/id_ed25519.pub
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIJhTIBt2zCmS/L8GQaNlpdlx12STrY2pWkGX+YFxU7J+ corcoras.git@protonmail.com
shaun@x1:~/study/vim_masterclass$

Go to GitHub → Settings → SSH and GPG keys → New SSH key → Paste it there.
```
4. Change remote URL to ssh
```
export GH_USERNAME='corcorasgit'
env | grep GH

git remote set-url origin git@github.com:$GH_USERNAME/vim_masterclass.git
```
Now git push will work without asking for a username/password.

## setup vim
```
edit the following file 
sudo vim /etc/vim/vimrc

set syntax
set number
set realtivenumber
set ruler
set hls 
set incseach
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
| 80i then * then esc | inserts a line of ****** |
| o  | insert below cursor new line |
 5o then # then esc | inserts 5 rows of # |
| 5o then 10.1.1 then esc | creates 5 network ip addresses |
| O  | insert above cursor new line |
| a  | append after the cursor |
| A  | append at the end of the line |
| r | cursor over the character then its replaced |
| $${\color{green}cw}$$ | change the word- deletes the word and places you in insert mode |
| $${\color{green}c\$}$$ | change from the cursor to the end of the line |
| $${\color{green}C}$$ | change from the cursor to the end of the line |
| $${\color{green}cc}$$ | change the whole line - places in insert mode |
| $${\color{green}~~}$$ | changes the case of a character |
| $${\color{green}g~W}$$| changes the case of the whole word |
| $${\color{green}g~~}$$ | changes the case of the whole word |
| $${\color{green}g~\$}$$ | changes the case of the whole word |
| $${\color{green}gUW}$$ | changes all characters to uppercase regardless |
| $${\color{green}gUU}$$ | changes the whole line to uppercase |
| $${\color{green}guu}$$ | changes the whole line to lowercase |
| $${\color{green}J}$$ | joins current line to the bottom line and adds a space |
| $${\color{green}5J}$$ | joins current line to the 5 bottom line and adds a space |
| $${\color{green}gJ}$$ | joins current line to the bottom line no spaces |





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


## Cut and Paste
```
### Cut-Copy-Paste  ==  delete-yank-put
```
| Command | Action |
| :---:  | :--- |
| u  | undo |
| yy | yank (copy) a line |
| 2yy | yank (copy) 2 lines |
| yw | yank (copy) the characters of the word from the cursor position to the start of the next word |
| 2yw | yank (copy) two words |
| yiw | yank (copy then insert) word under the cursor |
| yaw | yank (copy) word under the cursor and the space after or before it |
| y$ or Y | yank (copy) to end of line |
| p | put (paste) the clipboard after cursor |
| P | put (paste) before cursor |
| "1p | puts (paste) the contents of clipboard 1 |
| gp | put (paste) the clipboard after cursor and leave cursor after the new text |
| gP | put (paste) before cursor and leave cursor after the new text |
| dd | delete (cut) a line |
| 2dd | delete (cut) 2 lines | 
| dw | delete (cut) the characters of the word from the cursor position to the start of the next word |
| diw | delete (cut) word under the cursor |
| daw | delete (cut) word under the cursor and the space after or before it |
| d$  | start at cursoer and delete to the end of the line |
| :3,5d | delete lines starting from 3 to 5 |
| :reg | view all the clipboard registers |
| :reg z | views the z register |
| "Jyy| appends line to "J" register |
| 5"zp | pastes register z 5 times "[count][register]operator or [register][count]operator" |
| "ayy | yanks (copies) line into register "a" |
| :2p  | paste (put) register 2  in document |
| xp   | will swap character think if becomes fi (when cursor on i) |


## Substitutions and Transforming
### 
syntax here

| Command | Action |
| :---:  | :--- |
| $${\color{green}fb}$$ | finds the first occurance of the character "b" |
| $${\color{green}fA}$$ | finds the first occurance of the character "A", notice its case sensitive |
| $${\color{green}Fb}$$ | finds (looking backwards) next occurance of "b" |
| $${\color{green}Fb}$$ | ; finds  next occurance of "b" on the line of text |
| $${\color{green}Fb}$$ | , finds  previous occurance of "b" on the line of text |
| \and | , finds  and in the body of the document n for next N to find previous |
| $${\color{green}:nohls}$$ | remove highlighting |
| $${\color{green}:set \  hls}$$ | enables highlighting |
| $${\color{green}:*}$$ | place cursor over what you want to search then repeat * will act the same as next |
|  |  |
|   |  |
|  |  |
|   |  |
|  |  |
|   |  |
|  |  |
|   |  |
|  |  |
|   |  |
|  |  |
|   |  |
|  |  |
|   |  |
|  |  |
|   |  |
|  |  |