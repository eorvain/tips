ruby / rbenv / bundler / gem

https://github.com/rbenv/rbenv

# Install/Uninstall a Ruby version on the computer

```
rbenv install 3.2.2
```

```
rbenv uninstall 2.7.2
```


# Update the installable ruby versions

List the ruby versions installed on the computer. 
An asterix shows the active ruby version. The ruby active version change depending on the directory from which you launch the command.

```
rbenv versions
```

Si le fichier ~/.rbenv/plugin/ruby-build n'existe pas, alors éxécuter cette commande
```
git clone https://github.com/rbenv/ruby-build.git "$(rbenv root)"/plugins/ruby-build
```

Si le fichier existe, alors faire `git pull`dans le dossier `"$(rbenv root)"/plugins/ruby-build` ou `~/.rbenv/plugins/ruby-build `

```
# Vérifier que la mise à jour a bien été faite, la commande suivante doit lister les dernière mise à jour de ruby :
rbenv install --list-all
```

# Get version of ruby
```
# Get global version
rbenv global
# Get local version
rbenv local
```

# Set a version of Ruby
```
# changement local (version du dossier)
rbenv local 3.2.2
# changement global
rbenv global 3.2.2
rbenv global system
```

# Show the active system version
```
/usr/bin/ruby -v
```

# Show the active local version 

The local version is stored in `.ruby-version` of the directory

```
cat .ruby-version 
```