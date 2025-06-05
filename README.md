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
