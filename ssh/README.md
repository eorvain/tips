# SSH for gitlab
1- Create the public and private key

```
ssh-keygen -t rsa -b 2048 -C "email@example.com"
```

You'll see a response similar to:

```
Generating public/private rsa key pair.
Enter file in which to save the key (/home/user/.ssh/id_rsa):
```

File name exemple : id_gitlab_rsa

2 - Copy public key on Gitlab

```
cat id_gitlab_rsa.pub
```

3 - copy private key in .ssh/ folder

```
cp id_gitlab_rsa ~/.ssh/
```

4 - Edit config file

```
# Private GitLab instance
Host gitlab.viseo.com
  Preferredauthentications publickey
  IdentityFile ~/.ssh/id_gitlab_rsa
```

5 - ssh agent

```
eval $(ssh-agent -s)
ssh-add ~/.ssh/id_gitlab_rsa
```

