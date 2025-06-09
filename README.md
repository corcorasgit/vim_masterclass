<span style="color:red">
<h2> VIM_Masterclass</h2>
</span>
VM Masterclass course on Undemy

## notes on GIT
### setting up ssh keys

Text content


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
ssh-ed25519 AAAAC3NzacorcoranAAAAIJhTIBtshaunGQaNlpdlx12STrY2pWkGX+YFxU7J+ corcoras.git@protonmail.com
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

<span style="color:red">
<h2>setup vim</h2>
</span>

```
edit the following file 
sudo vim /etc/vim/vimrc

set syntax
set number
set realtivenumber
set ruler
set hls 
set incsearch
set shiftwidth=4
```

[comprehensive vim cheat sheet](https://vim.rtorr.com/)

<span style="color:red">
<h2> VIM_Cursor Motion Keys</h2>
</span>

| Navigation  | Description |  
| :----------: | :--------- | 
| h  | move cursor right |
| l  | move cursor left |
| j  | move cursor down |
| 2j | move 2 line down |
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

<span style="color:red">
<h2>Entering Text</h2>
</span>

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
| cw | change the word- deletes the word and places you in insert mode |
| c\$ | change from the cursor to the end of the line |
| C | change from the cursor to the end of the line |
| cc | change the whole line - places in insert mode |
| ~~ | changes the case of a character |
| g~W| changes the case of the whole word |
| g~~ | changes the case of the whole word |
| g~w | changes the case of the whole word |
| gUW | changes all characters to uppercase regardless |
| gUU | changes the whole line to uppercase |
| guu | changes the whole line to lowercase |
| J | joins current line to the bottom line and adds a space |
| 5J | joins current line to the 5 bottom line and adds a space |
| gJ | joins current line to the bottom line no spaces |





<span style="color:red">
<h2>Screen Navigation </h2>
</span>

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

##### syntax:  
### s/old/new
### [range]s[ubstitute]/{pattern}/{string}/[flags] [count]


| Command | Action |
| :---:  | :--- |
| fb | finds the first occurance of the character "b" |
| fA | finds the first occurance of the character "A", notice its case sensitive |
| Fb | finds (looking backwards) next occurance of "b" |
| Fb | ; finds  next occurance of "b" on the line of text |
| Fb | , finds  previous occurance of "b" on the line of text |
| \and | , finds  and in the body of the document n for next N to find previous |
| :nohls | remove highlighting |
| :set \  hls | enables highlighting |
| :* | place cursor over what you want to search then repeat * will act the same as next |
| :33,42s/net/org/g | substitutes lines 33 thru 43 replaces net with org |
| :\%s/net/org/g | % represents the whole document -  replaces net with org |
| :1,\$s/net/org/g | 1,$ == represents the whole document -  replaces net with org |
| :/Global/,/Local/s/net/org/g | pattern looks for Global and Local -  replaces net with org |
| | Summary - Same Line Searching |
| f{char} | Forward search |
| F{char} | Reverse search |
| t{char} | Forward till search |
| T{char} | Reverse till search |
| ; | Repeat in the same direction |
| , | Repeat in the opposite direction |
| /{pattern} | Foward search |
| ?{pattern} | Reverse search |
| n | Repeat search in the same direction |
| N | Repeat search in the opposite direction |
| * | Forward search for word |
| # | Reverse search for word |
| search format | :[range]s/{pattern}/{string}/{string}/flags |
| global sub | :%s/{pattern}/{string}/{string}/g

## Visual Mode


| Command | Action |
| :---:  | :--- |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
