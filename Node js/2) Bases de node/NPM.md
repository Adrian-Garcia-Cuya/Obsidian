Es un sistema de gestion de paquetes por defecto para *node js*.

# Inicializar un proyecto
El comando **npm init** se utiliza para inicializar un proyecto. Cuando se ejecuta este comando se crea un archivo *package.json*.

# Package
Es el punto inicial de cualquier aplicacion en *node.js*. Ayuda a visualizar que comandos se pueden utilizar y que paquetes estan instalados en un proyecto para ejecutar la aplicacion.

![[package.png]]

Podemos visualizar los comandos en la propiedad *scripts*:
![[package-script.png]]

Los paquetes instalados se pueden ver en la propiedad *dependencies*:
![[package-dependencies.png]]

Tambien se puede instalar depedencias para solo el entorno de desarrollo de la siguiente manera:

```
npm install nodemon --save-dev
```

En este ejemplo de instala la dependencia nodemon solo para el ambiente de desarrollo. Ademas, en el package.json se crea otra propiedad:

![[Pasted image 20240517173600.png]]

En *devDependencies* iran todas las dependencias instaladas para el entorno de desarrollo.

# Versionado semantico (Semantic Versioning)
El versionando semantico o *SemVer (Semantic Versioning)* es la forma recomendada de versionar paquetes. Normalmente se versiona de la siguiente manera 2.3.5 **(major.minor.patch)**

![[semver.png]]

- **Bug fix/patch version**  
Incluye correcciones de bugs, errores de documentación, gramaticales, etc.
- **Minor version**  
Incluye nuevas API’s (endpoints) o funcionalidades que no rompen nada de las versiones anteriores, de modo que lo que funciona en v1.1.0 debería funcionar también en v1.9.0.
- **Major version**  
Incluye código que rompe las cosas.  Puede ser la eliminación de API’s o el cambio de nombre de funciones de modo que lo que funciona en v1.0.0 no funcionará necesariamente en v2.0.0

#### Importante - uso del simbolo "^" y "~"
Normalmente en los paquetes se suele ver estos simbolos como el *caret "^"* o la *virgulilla "~"* antes de la version. Veamos como funciona cada uno.

- **Simbolo** `caret "^"`: indica a npm que puede seleccionar cualquier version que este en el rago de la *minor version*; de la version especificada. Por ejemplo, se tiene la version `^2.5.4`. Npm podra tomar el siguiente rango de versiones: `>= 2.5.4 < 3.x.x`. Entonces, los posibles valores seria: `2.5.6`, `2.7.10`, `2.9.6`.
- **Simbolo** `virgulilla "~"`: indica a npm que puede seleccionar cualquier version que este en el rago de la *patch version*; de la version especificada. Por ejemplo, se tiene la version `~2.5.4`. Npm podra tomar el siguiente rango de versiones `>= 2.5.4 < 2.6.0`.  Entonces, los posibles valores seria: `2.5.6`, `2.5.10`, `2.5.15`.

En la mayoria de casos, por defecto, cuando se instala un paquete, la version ya aparece con el simbolo *caret*. Esto con la finalidad de que cuando el proyecto se instale en otra maquina o se vuelva a instalar luego de un tiempo, npm pueda buscar si hubo una actualizacion para *minor version*, este caso por el simbolo *caret*, y asi obtener las ultimas mejoras del paquete.

# Package-lock
Es un archivo que genera automáticamente npm al instalar un paquete, el cual, registrar las versiones exactas de las dependencias instaladas en un proyecto de *node.js*.

Garantiza que se instalen las mismas versiones de las dependencias en todos los entornos, asegurando consistencia y evitando problemas de compatibilidad.

Veamos un ejemplo:
**package.json**
```json
{
  "dependencies": {
    "express": "^4.17.1"
  }
}
```
Esto permite instalar cualquier versión compatible de `express` como `4.17.2`, `4.18.0`, etc.

**package-lock.json**
```json
{
  "name": "tu-proyecto",
  "version": "1.0.0",
  "lockfileVersion": 2,
  "requires": true,
  "packages": {
    "": {
      "dependencies": {
        "express": "^4.17.1"
      }
    },
    "node_modules/express": {
      "version": "4.18.1",
      "resolved": "https://registry.npmjs.org/express/-/express-4.17.1.tgz",
      "integrity": "sha512-abc..."
    }
  }
}
```
Se especifican la dependencias instaladas en *dependencies* (son las mismas dependencias que estan en el archivo package.json) y las versiones especificas instaladas en el aplicacion estan en *node_modules/"dependency_name"*, y esa es la version especifica que se instalo en la aplicacion y la que se instalara en otras maquinas, sea el caso.

# Instalar paquetes
Para poder realizar la instalacion de paquetes de terceros se debe ejecutar el siguiente comando:
```
npm install "package_name"
npm install colors

-- Forma abreviada
npm i colors
```

## Eliminar una dependencia
Para desinstalar una dependencia solo se debe ejecutar el siguiente comando:
```
npm uninstall "dependency_name"
npm uninstall nodemon
```

## Indicar una version especifica para la instalacion
```
npm i "dependency_name"@"version"
npm i colors@1.0.0
```

# Node modules
node_modules es la carpeta donde se almacenan todas las dependencias y librerías que utiliza una aplicacion de node js para su correcto funcionamiento

