# config-repo (Gas Mapocho)

Configuracion de los microservicios. La sirve `config-server` (puerto 8888); cada servicio pide el archivo que
lleva su `spring.application.name`.

- `application.properties`: valores comunes a todos (Eureka y secreto JWT de desarrollo).
- `<servicio>.properties`: base de datos, RabbitMQ, rutas del gateway y Circuit Breaker de cada servicio.

Aqui no se escriben usuarios ni contrasenas: la base de datos usa `${DB_USER}` y `${DB_PASSWORD}`, que cada quien
define como variable de entorno en su PC. Despues de cambiar un archivo hay que hacer commit y push en este repo
y reiniciar el servicio afectado para que lea el valor nuevo.
