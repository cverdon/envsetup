# Update Packages

```
sudo apt update
sudo apt upgrade
```

# Prettify with PowerLine

- Reference : https://www.hanselman.com/blog/how-to-make-a-pretty-prompt-in-windows-terminal-with-powerline-nerd-fonts-cascadia-code-wsl-and-ohmyposh

## Shell

```
sudo apt install golang-go
go install -u github.com/justjanne/powerline-go
```

## Config

Add this to your ~/.bashrc

```
GOPATH=$HOME/go
function _update_ps1() {
    PS1="$($GOPATH/bin/powerline-go -error $?)"
}
if [ "$TERM" != "linux" ] && [ -f "$GOPATH/bin/powerline-go" ]; then
    PROMPT_COMMAND="_update_ps1; $PROMPT_COMMAND"
fi
```

## Important Note

GOTCHA: If you are using WSL2, it'll be lightning fast with git prompts if your source code is in your Ubuntu/Linux mount, somewhere under ~/.

# HTOP

Process and system resources viewer.

```
sudo apt install htop
```

# GIT

## Shell

```
sudo apt install git
```

## Configure

- Reference: https://dev.to/matowang/quick-guide-setup-github-ssh-keys-on-linux-servers-5ena#:~:text=Setup%20GitHub%20ssh%20keys%20on%20Linux%20servers%20in,6%206.%20Pull%20from%20your%20GitHub%20Repo%20

https://dev.to/matowang/quick-guide-setup-github-ssh-keys-on-linux-servers-5ena#:~:text=Setup%20GitHub%20ssh%20keys%20on%20Linux%20servers%20in,6%206.%20Pull%20from%20your%20GitHub%20Repo%20

- Configure Git

```
git config --global user.name "bob"
git config --global user.email bob@mail.com
#git config --global credential.helper=store --file ~/.git-credentials <- not needed for ssh
```

- Configure SSH Key
```
ssh-keygen -t ed25519 -C "bob@mail.com" 
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
cat ~/.ssh/id_ed25519.pub 
# Copy public key
# Create & Paste into GitHub deploy keys
git clone git@github.com:USER/foo.git
```

#lynx
Terminal text based web browser

```
sudo apt install lynx
```


#pandoc

Convert and view markdown to HTML in the terminal

```
sudo apt install pandoc
pandoc filename.md -t html | lynx -stdin
```
