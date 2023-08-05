Los volúmenes permiten la persistencia de los datos.

Tipos de volúmes:
- Named Volumes
Nosotros mismo asignamos el nombre al volúmen.

Veamos un ejemplo:
```Docker
docker volume create todo-db
docker run -v todo-db:/etc/todos getting-started
```

- Bind volumes
Se utiliza para vincular un filesystem del host con un filesystem de contenedor.
Esto trabaja con paths absolutos.

Veamos un ejemplo:
```Docker
-v "$(pwd):/app"
```

- Anonymous Volumes
Indicamos a docker que agregue un nombre al volúmen.
Sólo se especifica el path del contenedor y Docker lo asigna automáticamente
en el host.

Veamos un ejemplo:
```Docker
docker run -v /var/lib/mysql/data
```

