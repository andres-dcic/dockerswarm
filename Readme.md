Docker Swarm

# Verificar setup Docker Swarm.
```
sudo docker node ls
```

```
sudo docker stack ls
sudo docker ps
sudo docker-compose down
```

# Migrar la app a Docker Swarm

```
docker build -t andr35/myflask:v0.1.0 .
```
* Modificar el docker-compose  para usar la imagen buildeada anteriormente
```
docker stack deploy --compose-file docker-compose.yml myapp
```

```
docker stack ls
docker stack services myapp
docker service logs -f myapp_web
docker service ps myapp_web
docker service update --force myapp_web
docker service rm disml3ux1mye
docker stack deploy --compose-file docker-compose.yml myapp
curl node1:5000
docker service scale myapp_web=3
```

