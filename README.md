# Laboratorio 02

Hoy utilizaremos docker compose para poder desplegar 3 copias de una API. 
# Stack
API
 -  Minimal API
 - Debe retornar un mensaje
 - Docker BD
 - PostgreSQL

# Indicaciones
## Comandos

```bash
#1. Construir las imágenes locales
docker compose up --build
```
``` bash
# Coroborar que esta corriendo
docker compose ps
```
``` bash
# Las replicas
curl -i http://localhost:3000/
curl -i http://localhost:3001/
curl -i http://localhost:3002/
```

```bash
#Mostrar informacion detallada del volumen local
docker volume ls
```

## Configuracion por entorno
```bash
POSTGRES_PASS=TU_CONTRASEÑA
MESSAGE1=NOMBRE1
MESSAGE2=NOMBRE2
MESSAGE3=NOMBRE3
POSTGRES_USER=TU_USARIO
POSTGRES_PASS=TU_CONTRASEÑA_POST
POSTGRES_DB=TU_BD
```



# Tipos de redes que existen en docker
- **`bridge`**: Es como un puente que conecta a todos los contenedores cuando se levanta un proyecto en docker. Es la red por defecto.
- **`host`**: El contenedor usa de forma directa la red de la maquina sin aislar, lo que implica menos seguridad. Asociado a Docker Swarm.
- **`none`**: Usado para casos de seguridad extrema, pues en este caso, el contenedor no tiene acceso a ninguna red.
- **`overlay`**: Conecta contenedores de distintas maquinas entre si.
- **`ipvlan`**: Es menos comun. El contenedor tiene su propia direccion IP compartiendo la MAC del host.
- **`macvlan`**: Asigna al contenedor una direccion MAC propia, lo que le hace parecer una maquina indepentiente(como si no fuera un contenedor).


# Tipos de volumen que existen en docker
- **`Volumes`**: Son creados y gestionados directamente por docker. Eso permite que sean mas faciles de respaldar y migrar. Existen dos categorias: Named volumes y Anonymous volumes. En este proyecto se uso el primero, asignado con nombre `db_data`
- **`Bind mounts`**: Conecta una carpeta que ya existe en la maquina del host con una ruta dentro del contenedor.
- **`tmpfs mounts`**: Vive solo en memoria RAM por lo que no persisten en disco. Lo que provoca que cuando el contenedor se apaga, se pierdan los datos. 

# Creditos
- Gomez Salinas Yessica Pamela
- 000284313
# Referencias
- https://hub.docker.com/r/nmatsui/hello-world-api
- https://hub.docker.com/_/postgres
- https://docs.docker.com/engine/storage/volumes/
- https://docs.docker.com/engine/network/
