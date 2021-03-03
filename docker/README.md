Lister les containers actifs

```
docker ps
```

Lister les containers actifs et stoppés :

```
docker ps -a
```

Arrêter un container :

```
docker container stop id
```

Arréter tous les containers :

```
docker stop $(docker ps -a -q) 
```

Se connecter en bas à un container :

```
docker exec -i -t id bash
```

Relancer appache depuis un container :

```
# /etc/init.d/apache2 reload
```