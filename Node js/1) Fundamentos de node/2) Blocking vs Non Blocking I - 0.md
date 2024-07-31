# Blocking
Este tipo de operacion bloquea el flujo de proceso de la aplicacion hasta que se termine una determinada tarea (como leer un archivo o una solicitud hacia la base de datos).

Esto puede causar ciertos problemas cuando las aplicaciones deban manejar multiples solicitudes debido a que se tendria que esperar a que termine cada solicitud para continuar con la siguiente.

# Non Blocking
Estas operaciones no esperan a que el proceso termine, en cambio, permite que el flujo del programa continue. Para esto se debe brindar un callback que se ejecutara cuando el proceso finalice.

