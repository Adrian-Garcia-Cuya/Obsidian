# ¿Qué es?
Es una herramienta que ayuda a construir imágenes de forma optima y que estas seas multiplataforma/multiples arquitecturas.

# Construcción en múltiples arquitecturas
Listar las construcciones existentes:
```Docker
docker buildx ls
```

De forma predeterminada, se mantiene seleccionado la imagen predeterminada.

Para crear una nueva construcción (builder) se debe realizar lo siguiente:

```Docker
docker buildx create --name mybuilder --driver docker-container --bootstrap
mybuilder
```

Luego, se debe seleccionar el nuevo builder creado:
```Docker
docker buildx use mybuilder
```

## Construir y pushear la imagen
Para ejecutar cada layer del dockerfile y luego pushearlo a dockerhub se debe realizar el siguiente comando:
```Docker
docker buildx build --platform linux/amd64,linux/arm64,linux/arm/v7 -t <username>/<image>:latest --push .
```
- `<nombre de usuario>` debe ser un ID de Docker válido y `<imagen>` y un repositorio válido en Docker Hub. 
- El indicador `--platform` informa a buildx para crear imágenes de Linux para arquitecturas AMD de 64 bits, Arm de 64 bits y Armv7. 
- El indicador `--push` genera un manifiesto de varias arquitecturas y envía todas las imágenes a Docker Hub. 
### Inspeccionar un builder
Al inspeccionar el builder podemos visualizar las plataformas en las que serán compatibles la imagen.
```Docker
docker buildx inspect
```
###### Nota - shotcut
Se puede crear el builder y seleccionarse en un mismo comando:
```Docker
docker buildx create --name mybuilder --driver docker-container --bootstrap --use
```


