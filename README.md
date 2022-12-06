### generate rsa ssh key

```ssh-keygen -t rsa -b 4096```

### private key

```cat ~/.ssh/{NAME}```

### public key

```cat ~/.ssh/{NAME}.pub```

### add key to local ssh agent

```ssh-add -l```

```ssh-add ~/.ssh/{NAME}```

### add key to remote server (not used for GIT)

```ssh-copy-id -i ~/.ssh/{NAME} {USER}@{HOST}```

### test connection

```ssh -T git@github.com```

```ssh -T git@ssh.dev.azure.com```

### test connection (verbose)

```ssh -v git@github.com```

```ssh -v git@ssh.dev.azure.com```

```
Host github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/{NAME}
```

```
Host ssh.dev.azure.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/{NAME}
```

```
Host example.com
  AddKeysToAgent yes
  UseKeychain yes
  User {LOGIN USER}
  IdentityFile ~/.ssh/{NAME}
```
