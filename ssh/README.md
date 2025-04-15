# SSH for gitlab
1- Create the public and private key

```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

You'll see a response similar to:

```
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/user/.ssh/id_ed15519):
```

File name exemple : id_gitlab_25519

2 - Copy public key on Gitlab

```
cat id_gitlab_ed15519.pub
```

3 - copy private key in .ssh/ folder

```
cp id_gitlab_ed15519 ~/.ssh/
```

4 - Edit config file

```
# Github
Host github.com
  # AddKeysToAgent yes
  # UseKeychain yes
  # IdentityFile ~/.ssh/id_ed25519
```

5 - ssh agent

```
eval $(ssh-agent -s)
```

6 - add key from ssh

```
ssh-add ~/.ssh/id_ed25519
```

7 - remove key from ssh

```
ssh-add -d ~/.ssh/id_ed25519
```



