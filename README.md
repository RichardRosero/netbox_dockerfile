#                                            netbox_dockerfile
# imagen de la comunidad y configuracion #
## ----------------hacer todo esto en el directorio donde descargas la imagen-------------------------###

# clona la imagen mantenida por la comunidad #
```
git clone -b release https://github.com/netbox-community/netbox-docker.git
```
# entra a la carpeta que se creo al descargar el netbox#
```
cd netbox-docker
```
# crea, copia y pega la siguiente informacion para crear el servicio compose de netbox #
```
tee docker-compose.override.yml <<EOF
version: '3.4'
services:
  netbox:
    ports:
      - 8000:8080
EOF
```
# ejecuta los comandos siguientes en la consola #
```
docker compose pull
docker compose up
```

# crea super usuario ya que usamos django #
```
docker compose exec netbox /opt/netbox/netbox/manage.py createsuperuser
```

# dirigite despeus de unos minutos al link #
```
docker compose exec netbox /opt/netbox/netbox/manage.py createsuperuser
```
