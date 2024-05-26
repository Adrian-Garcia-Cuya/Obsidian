El comando `shutdown` prepara el sistema para un apagado seguro. Todos los usuarios que iniciarion sesion reciben un mensaje/notificacion de que el sistema se apagara.

```
shutdown [OPCIONES] HORA [MENSAJE]
```

Este comando require un argumento de tiempo para indicar cuando comenzara el apagado. Los argumentos pueden ser `now` (hora), una hora del dia con el siguiente formato `hh:mm` o el numero de minutos antes de apagarse `+minutos`'

Ejemplos:
```
//Ejemplo 1 (now)
root@localhost:~# shutdown now
//Ejemplo 2 (hh:mm)
root@localhost:~# shutdown 01:51
//Ejemplo 3 (+minutos)
root@localhost:~# shutdown +5
```

Adicionalmente, se puede brindar un mensaje como argumento, el cual, se mostrara a todos los usuarios.

```
root@localhost:~# shutdown +1 "Goodbye World!"
```

#### Nota
El comando `shutdown` requiere acceso administrativo.