# tips zsh

# Create zsh aliases

## Create .zshrc
```
vim ~/.zshrc
```

Copy / paste :

```
# .zshrc

# Source global definitions
if [ -f /etc/zshrc ]; then
. /etc/zshrc
fi

# User specific aliases and functions
if [ -f ~/.zsh_aliases ]; then
. ~/.zsh_aliases
fi

```
## Create .zsh_aliases

```
vim ~/.zsh_aliases
```
Copy / Paste :
```
alias realias='. ~/.zshrc'
alias vali='vim ~/.zsh_aliases'
alias la='ls -al'
alias cdw='cd ~'
```

## Start aliases
```
. ~/.zshrc
vali
```

