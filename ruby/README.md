
https://github.com/rbenv/rbenv

# Install a new version of ruby
Si le fichier ~/.rbenv/plugin/ruby-build n'existe pas, alors éxécuter cette commande
```
git clone https://github.com/rbenv/ruby-build.git "$(rbenv root)"/plugins/ruby-build
```

Si le fichier existe, alors faire `git pull`dans le dossier `plugin/ruby-build`

```
# Vérifier que la mise à jour a bien été faite :
rbenv install --list-all
```

# Get version of ruby
```
# Get global version
rbenv global
# Get local version
rbenv local
```

# install a Ruby version:
```
rbenv install 3.2.2
````

# choose local Ruby version 3.2.2:
```
rbenv local 3.2.2
```

# choose global Ruby version 3.2.2:
```
rbenv global 3.2.2
rbenv global system
```

# system version
```
/usr/bin/ruby -v
```

# local version 
```
cat .ruby-version 
```