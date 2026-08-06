# erp-software-architecture

Este repositorio es la entrega del taller de **Arquitectura de Software**, donde diseñé la arquitectura de un sistema **ERP**, siguiendo un enfoque ágil y documentando todo con la plantilla **arc42**.

- 🔗 **Repositorio**: https://github.com/diego311204/erp-software-architecture
- 🔗 **Backlog en Jira**: https://academia-team-l9s11f4z.atlassian.net/jira/software/projects/KAN/list?jql=project+%3D+KAN+ORDER+BY+cf%5B10019%5D+ASC

## Qué incluye este taller

- Backlog con épicas e historias de usuario para los **6 módulos del ERP** (Compras, Facturación, Stock/Costos, Activos Fijos, Empleados y EIS), gestionado en Jira/Notion, con sus criterios de aceptación en formato Dado-Cuando-Entonces.
- Diagramas de arquitectura hechos en **PlantUML**: contexto (C1) y contenedores (C2), que muestran cómo interactúan los 6 módulos con el sistema.
- Un diseño detallado (diagrama de secuencia y modelo de datos) tomando como ejemplo el **módulo de Compras**, tal como pedía el taller.
- Documentación de arquitectura siguiendo la plantilla **arc42**.

## Documentos importantes

| Archivo | Qué contiene |
|---|---|
| [`01_introduction_and_goals.md`](./01_introduction_and_goals.md) | Objetivo general del ERP y sus 6 módulos, requisitos de negocio del módulo de Compras y metas de calidad. |
| [`02_architecture_constraints.md`](./02_architecture_constraints.md) | Tecnologías escogidas (React, Spring Boot, PostgreSQL) y restricciones del proyecto. |
| [`03_system_scope_and_context.md`](./03_system_scope_and_context.md) | Contexto de negocio con los 6 roles de usuario y el diagrama C1. |
| [`05_building_block_view.md`](./05_building_block_view.md) | Diagrama de contenedores (C2) y modelo de datos (MER) del módulo de Compras. |
| [`06_runtime_view.md`](./06_runtime_view.md) | Diagrama de secuencia del escenario "Generar Orden de Compra". |
| [`07_deployment_view.md`](./07_deployment_view.md) | Cómo se desplegaría el sistema (Docker: Nginx + API + PostgreSQL). |
| [`10_glossary.md`](./10_glossary.md) | Glosario de términos del dominio del ERP. |

## Los 6 módulos del ERP

- **Compras**: productos, proveedores y órdenes de compra.
- **Facturación**: facturas de venta y clientes.
- **Stock/Costos**: inventario y costos.
- **Activos Fijos**: control y depreciación de activos.
- **Empleados**: nómina, asistencia y vacaciones.
- **EIS**: reportes e indicadores para el gerente.

Cada uno tiene su propia épica con historias de usuario en el backlog de Jira/Notion. El detalle técnico (diagramas de secuencia y modelo de datos) se hizo sobre el módulo de Compras como caso de estudio, pero la arquitectura general (C1 y C2) contempla los 6 módulos funcionando dentro del mismo sistema.

## Imágenes de los diagramas

Todas las imágenes de los diagramas están en la carpeta [`images`](./images), y son referenciadas desde los archivos `.md` de arriba.

## Cómo está organizado el backend/frontend (arquitectura elegida)

- **Frontend**: SPA hecha en React.
- **Backend**: API monolítica en Java con Spring Boot, que maneja la lógica de los 6 módulos.
- **Base de datos**: PostgreSQL.

Más detalle de por qué se escogió esta arquitectura está en `02_architecture_constraints.md` y `05_building_block_view.md`.
