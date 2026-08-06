# Introducción y Metas

## Vista de Requerimientos

El sistema que estoy diseñando es un **ERP**, que básicamente es un programa que junta en un solo lugar los procesos importantes de una empresa, para que no se manejen por separado en Excel o en la cabeza de cada persona.

El ERP tiene 6 módulos:

- **Compras**: para registrar productos, proveedores y hacer pedidos.
- **Facturación**: para hacerle facturas a los clientes.
- **Stock/Costos**: para saber cuánto inventario hay y cuánto cuesta.
- **Activos Fijos**: para llevar el control de las cosas de la empresa (equipos, muebles, etc.).
- **Empleados**: para manejar la nómina y la asistencia.
- **EIS**: para que el gerente vea reportes e indicadores.

Me enfoqué en el **módulo de Compras** para este taller.

### Lo que debe poder hacer el módulo de Compras

1. Registrar productos con su nombre, descripción y unidad de medida.
2. Registrar proveedores y poder ponerles un precio a los productos que venden.
3. Generar una orden de compra escogiendo un proveedor y los productos que se necesitan.
4. Registrar cuando llega la mercancía de una orden de compra, para que se sume al inventario.
5. Poder ver el historial de compras que se le han hecho a un proveedor.

## Metas de Calidad

Estas son las cosas que más me importa que el sistema cumpla, en orden de importancia:

| Prioridad | Meta | Por qué |
|---|---|---|
| 1 | Que sea fácil de usar | La gente de compras y bodega no necesariamente sabe de tecnología, entonces la interfaz tiene que ser sencilla. |
| 2 | Que los datos no se dañen | Si algo queda mal registrado, el inventario y los costos quedan mal también. |
| 3 | Que esté disponible | El sistema se necesita en horario de trabajo, si se cae se frena todo. |
| 4 | Que sea fácil de mantener | Como el sistema tiene varios módulos, debo poder agregarle o arreglarle cosas sin dañar lo demás. |

## Partes interesadas (Stakeholders)

| Rol | Contacto | Qué espera del sistema |
|---|---|---|
| Gestor de Compras | Equipo de Compras | Poder registrar productos y proveedores, y hacer pedidos rápido. |
| Encargado de Bodega | Equipo de Inventario | Que el inventario quede bien actualizado cuando llega mercancía. |
| Gerente | Dirección | Poder ver reportes confiables para tomar decisiones. |
| Yo (autor del taller) | Grupo X | Construir el sistema aplicando lo que he visto en la materia. |
| Profesor | Curso de Arquitectura de Software | Revisar que el diseño esté bien hecho según lo enseñado en clase. |
