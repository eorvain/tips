# tips bash

# Create bash aliases

## Create .bashrc
```
vim ~/.bashrc
```

Copy / paste :

```
# .bashrc

# Source global definitions
if [ -f /etc/bashrc ]; then
. /etc/bashrc
fi

# User specific aliases and functions
if [ -f ~/.bash_aliases ]; then
. ~/.bash_aliases
fi

```
## Create .bash_aliases

```
vim ~/.bash_aliases
```
Copy / Paste :
```
alias realias='. ~/.bashrc'
alias vali='vim ~/.bash_aliases'
alias la='ls -al'
alias cdw='cd ~'
```

## Start aliases
```
. ~/.bashrc
vali
```

