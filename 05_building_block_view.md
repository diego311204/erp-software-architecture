# Vista de Bloques

## Sistema General de Caja Blanca

Ahora sí "abro" la caja negra del ERP para ver qué tiene adentro. Este es el diagrama de contenedores (C2):

![Diagrama de Contenedores](./images/ZOOM%20ERP.png)

**Por qué lo armé así**: escogí una arquitectura monolítica (todo el backend junto) porque es un taller y no hace falta complicarse con microservicios. Aun así, separé bien las responsabilidades: una parte se encarga solo de la interfaz, otra de la lógica, y otra de guardar los datos.

**Las piezas del sistema**: la aplicación web (SPA), la API y la base de datos.

**Cómo se hablan entre ellas**: la SPA le habla a la API por HTTPS/JSON, y la API le habla a la base de datos por JDBC.

### Single-Page Application (SPA)

Es la parte que ve el usuario en el navegador. Ahí es donde el Gestor de Compras, el Facturador, y los demás roles hacen todo (registrar productos, hacer órdenes de compra, ver reportes, etc.).

Se conecta con la API por HTTPS/JSON.

Como quiero que sea fácil de usar, esta parte tiene que quedar bien organizada y sencilla.

### API Monolítica

Es donde está toda la lógica de negocio de los 6 módulos. Aquí es donde se valida la información, se hacen los cálculos y se decide qué guardar en la base de datos.

Se conecta con la SPA (recibiendo peticiones) y con la Base de Datos (por JDBC) y con los sistemas externos (Contable y DIAN) por HTTPS/JSON.

Básicamente aquí se cumplen todas las reglas que puse en los criterios de aceptación de las historias de usuario.

### Base de Datos

Es donde queda guardada toda la información: productos, proveedores, órdenes de compra, facturas, inventario, activos, empleados, etc.

Solo la API puede hablar directamente con la base de datos, ningún otro componente le llega directo.

Me importa que los datos no se dañen ni queden inconsistentes, porque varios módulos dependen de la misma información (por ejemplo, Compras y Stock/Costos comparten el inventario).

### Modelo de datos (Módulo de Compras)

Para completar esta vista, este es el modelo de entidad-relación (MER) del módulo de Compras, que muestra cómo quedan estructuradas las tablas dentro de la Base de Datos:

![Modelo Entidad-Relación - Compras](./images/ERP%20ENTIDADES.png)

- **Producto** y **Proveedor** son las entidades base, y se relacionan mediante **Producto_Proveedor**, que guarda el precio que cada proveedor maneja para cada producto.
- **Orden_Compra** queda asociada a un proveedor, y sus productos con cantidades quedan en **Detalle_Orden_Compra**, que además guarda la cantidad recibida (para el proceso de recepción de mercancía).
