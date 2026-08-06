# Vista de Ejecución

## Escenario: Generar Orden de Compra

Escogí este escenario porque es uno de los procesos más importantes del módulo de Compras, y porque se ve claramente cómo interactúan los 3 bloques del sistema (SPA, API y Base de Datos).

Corresponde a esta historia de usuario:

> **HU-04**: Como gestor de compras, quiero generar una orden de compra seleccionando un proveedor y los productos requeridos con sus cantidades, para que pueda formalizar el pedido de mercancía.

![Diagrama de Secuencia - Generar Orden de Compra](./images/HISTORIA%20USUARIO%20ERP.png)

### Cómo funciona el flujo, paso a paso

1. El Gestor de Compras escoge en la pantalla un proveedor y los productos que necesita, con sus cantidades.
2. La SPA le manda esa información a la API.
3. La API revisa que todo esté bien (que el proveedor exista y que las cantidades no sean cero o negativas).
4. La API le pregunta a la base de datos cuáles son los precios que tiene ese proveedor para cada producto.
5. Con esos precios, la API calcula cuánto vale la orden completa.
6. La API guarda la nueva orden en la base de datos, y esta le devuelve un número consecutivo.
7. La API le responde a la SPA que todo salió bien, con el número y el total de la orden.
8. La SPA le muestra al usuario la orden ya generada, con estado "pendiente".

Con este flujo me aseguro de que no se pueda crear una orden sin proveedor válido y que el total siempre se calcule bien, que es justo lo que pedían los criterios de aceptación de esta historia.
