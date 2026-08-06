# Restricciones de la Arquitectura

Para este taller decidí usar una **arquitectura monolítica**, o sea, todo el backend en un solo bloque, en vez de dividirlo en varios servicios (microservicios). Escogí esto porque es más simple de armar y de entender, y para el tamaño de este proyecto no hace falta algo más complicado.

## Qué tecnologías decidí usar

- **Frontend (lo que ve el usuario)**: una aplicación en **React**, que corre en el navegador (a esto se le llama SPA - Single Page Application).
- **Backend (la lógica del sistema)**: una API hecha en **Java con Spring Boot**, que es la que maneja todas las reglas de negocio de los 6 módulos.
- **Base de datos**: uso **PostgreSQL** para guardar toda la información.
- **Cómo se comunican**: el frontend le habla al backend por internet usando **HTTPS**, mandando y recibiendo datos en formato **JSON**.
- El backend se conecta a la base de datos usando **JDBC** (la forma estándar en que Java habla con bases de datos).

## Cosas que me limitan o que tuve que tener en cuenta

- Soy estudiante (Grupo X), entonces preferí algo simple de mantener antes que algo súper escalable pero complicado.
- El taller pide documentar todo con la plantilla **arc42** y subirlo a un repositorio público en **GitHub**.
- Manejo el backlog y los sprints en **Jira/Notion**.
- El sistema tiene que poder mandarle información a un **sistema contable externo**.
- El sistema tiene que poder comunicarse con la **DIAN** para la facturación electrónica, porque en Colombia es obligatorio.
- Los diagramas los hice con **PlantUML** y quedan guardados junto con el código en el repositorio.
