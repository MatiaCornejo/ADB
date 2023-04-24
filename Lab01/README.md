# Como iniciar el cluster

## Motivación

Como vimos anteriormente, configurar el cluster puede ser una tarea difícil y aburrida :scream:.
Pero docker cuenta con **Docker Compose** quien sera nuestro salvador :smiley:

## Docker Compose

Encontraran disponible el archivo llamado **docker-compose.yml** quien permite ejecutar aplicaciones de docker en varios contenedores (justo lo que queremos hacer) :satisfied:, en el encontraran la definición del cluster, cantidad de nodos, configuración de semillas y red, para iniciar deben utilizar el siguiente comando

```bash
sudo docker compose -f docker-compose.yml up
```
Luego de eso se comenzará a construir el cluster junto a sus nodos, un poco de paciencia por favor :sleepy:

Cuando se construyan nuestros contenedores podremos listarlos con el siguiente comando:

```bash
sudo docker ps
```

Luego para comprobar el estado de conexión del cluster basta con ingresar a un nodo y visualizar el estado de la conexión:

```bash
sudo docker exec -it cluster_cassandra_nodo01 bash
```

Dentro del contenedor:

```bash
nodetool status
```

Y listo, tenemos nuestro cluster de cassandra! :sunglasses:

## To Do list

- [x] Creación Docker compose
- [ ] Creación de volumen persistente
- [ ] Creación automática del key space
- [ ] Varios

### Finalmente

Espero esto haya sido útil, cualquier duda, sugerencia y/o comentario será bien recibida, gracias por leer!:cat:
