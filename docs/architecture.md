# Arquitectura de Infraestructura

Este repositorio es responsable del orquestamiento local de los contenedores mediante Docker.

## Reglas Operativas
1. **Rol Limitado sobre la Base de Datos**: Docker levanta el motor de MySQL (8.4) con una base de datos vacía. **Bajo ningún concepto** se ejecutan sentencias DDL (CREATE TABLE) desde este repositorio.
2. **Control de Salud (Healthchecks)**: Servicios que dependan de MySQL deben usar `condition: service_healthy` para garantizar que la base de datos acepta conexiones antes de levantar el backend.
3. **Sin Migraciones**: El directorio `migrations/` no pertenece a este repositorio. Le pertenece al repositorio API.
