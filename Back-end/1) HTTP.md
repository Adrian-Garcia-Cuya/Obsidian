![[estructura_ruta.png]]

# Ciclo de una solicitud
1. El usuarios a través del navegador realiza una solicitud (request) con un dominio.
2. El sistema DNS se encarga de encontrar en que servidor se encuentra cierto dominio y envía el request.
3. El servidor (donde esta toda la arquitectura del back-end) va a responder de acuerdo al request.
4. Se realiza un response. Puede tener varios formatos. 
	- Front-end -> HTLM, CSS, JS
	- Datos -> XLM, JSON
5. Retorno de solicitud
![[ciclo_de_solicitud.png]]

# Códigos de estado
- 100 -> Información hacia los cliente que hacen la petición.
- 200 -> ok, se realizó con exito.
- 201 -> algo salio bien pero en estado de creación (subir registro, dato)
- 204 -> salio con exito pero no se retorna nada.
- 300 -> Redirect (se utiliza cuando se cambia la ruta antigua por una nueva)
- 301 -> Moved, indica que cierto recurso a sido movido a otra ruta.
- 307 -> temporary, || a sido movido temporalmente.
- 308 -> permanent || a sido movido permanentemente.
- 400 -> Client Error (sucede cuando el cliente envía información erronea)
- 401 -> Unauthorized, no se tiene permiso para ingresar a cierta página.
- 404 -> Not found, ocurre cuando se trata de ingresar a una página que no existe.
- 409 -> Conflict, cuando ocurre un conflicto al momento de enviar información del lado del cliente.
- 500 -> Server Error - Internal.
- 502 -> Bad gateway.
- 504 -> Gateway Timeout -> el tiempo de espera se agotó.

![[codigos-estado-http.png]]