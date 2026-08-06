# Alcance y Contexto del Sistema

## Contexto de Negocio

Acá muestro con quién interactúa el ERP: los usuarios que lo usan y los sistemas externos con los que se tiene que comunicar.

**Los usuarios (uno por cada módulo):**

- **Gestor de Compras**: registra productos, proveedores y hace las órdenes de compra.
- **Facturador**: hace las facturas y registra clientes.
- **Encargado de Bodega**: revisa y actualiza el inventario.
- **Encargado de Activos**: lleva el control de los activos fijos.
- **Encargado de Talento Humano**: maneja lo de empleados y nómina.
- **Gerente**: mira los reportes e indicadores (módulo EIS).

**Sistemas externos con los que se conecta:**

- **Sistema Contable Externo**: le llegan los asientos contables que genera el ERP.
- **Facturación Electrónica DIAN**: valida las facturas que el sistema genera, porque en Colombia toca reportarlas ante la DIAN.

Este es el diagrama de contexto (C1), que muestra el ERP como una "caja negra" (o sea, sin ver el detalle de adentro, solo con quién se conecta):

![Diagrama de Contexto](./images/sistema%20ERP.png)

## Contexto Técnico

Los usuarios usan el sistema desde un navegador, conectándose por **HTTPS**. Con los sistemas externos, el ERP se conecta también por internet, mandando y recibiendo información en formato **JSON**.

| Quién se conecta | Con quién | Cómo |
|---|---|---|
| Usuarios (todos los roles) | Sistema ERP | HTTPS (desde el navegador) |
| Sistema ERP | Sistema Contable Externo | HTTPS/JSON |
| Sistema ERP | Facturación Electrónica DIAN | HTTPS/JSON |
