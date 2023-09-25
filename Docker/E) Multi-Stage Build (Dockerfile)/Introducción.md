Cuando una imagen sufre un cambio en un determinado layer. Todo lo que se encuentre después se volverá a construir/ejecutar. Esto está bien en cierta parte pero hay partes en donde no será necesario que se reconstruya nuevamente y es ahí donde se utiliza este concepto de "multi-stage"

Veamos un ejemplo:

![[dockerfile-example-multi-stage.png]]

Supongamos que se tiene una imagen e identificamos las partes que se encargarán de realizar determinadas tareas (en este caso son 4).

Si en la primera etapa por x razones realizamos un cambio, todas las demás etapas se volverán a reconstruir y si el cambio realizado no afecta en nada a las demás o a algunas etapas no sería necesario que se tengan que volver a construir. Simplemente podrían tomar lo que ya se encuentra en caché y reconstruir la imagen más rápido.

# Multi-Stage
Este concepto reside en crear pequeñas imágenes temporales que realicen una determinada tarea. Cada una de estas imágenes estarán divididas por las etapas que se requieran.

Estas imágenes temporales van a permitir compartir información entre sí (cada una es independiente de la otra). Si se requiere algo que se construyó en otra imagen temporal solo se debe especificar que es lo que se requiere para poder compartir o enviar esa información a la otra imagen.

Veamos un ejemplo:
![[dockerfile-multi-stage.png]]

Al final de todo lo realizado, solo se exportará la última imagen, la cual es la que tiene todo lo necesario para el funcionamiento de nuestra aplicación web.