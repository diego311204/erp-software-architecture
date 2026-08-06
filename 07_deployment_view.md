# Vista de Despliegue

## Nivel de infraestructura 1

Para este taller pensé en un despliegue sencillo: todo corriendo en un solo servidor (por ejemplo, una máquina virtual en la nube). No hace falta más que eso para el tamaño de este proyecto.

**Por qué así**: como armé una arquitectura monolítica (solo 3 piezas: SPA, API y base de datos), no necesito varios servidores ni nada complicado. Con Docker alcanza para tener todo funcionando.

**Cómo quedaría organizado**:
- La **SPA** se sirve con un contenedor de **Nginx** (un programa que entrega archivos web).
- La **API** corre en su propio contenedor de **Spring Boot**.
- La **Base de Datos** corre en un contenedor de **PostgreSQL**, con un espacio aparte para que los datos no se pierdan si el contenedor se reinicia.
- Los tres contenedores se levantan juntos usando **Docker Compose**.

## Nivel de Infraestructura 2

### Servidor de la aplicación web

Contenedor con Nginx, que le entrega al navegador del usuario los archivos de la SPA (React), usando el puerto 443 (HTTPS).

### Servidor de la API

Contenedor con la API (Spring Boot). Recibe las peticiones que le manda la SPA, y también tiene salida a internet para hablar con el Sistema Contable Externo y con la DIAN.

### Servidor de la base de datos

Contenedor con PostgreSQL. Solo la API se puede conectar a este, no está expuesto directamente a internet, y tiene guardado un respaldo de los datos.
