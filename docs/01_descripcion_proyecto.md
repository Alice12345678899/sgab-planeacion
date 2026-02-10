# Descripción del Proyecto

## Objetivo del sistema
El Sistema de Gestión Académica Básico (SGAB) tiene como objetivo facilitar la administración de información académica, permitiendo registrar y consultar datos de alumnos, materias, calificaciones y usuarios de forma organizada y segura.

## Usuarios principales
Los usuarios principales del sistema son:
- Administrador académico
- Docentes
- Personal administrativo

Cada tipo de usuario interactúa con el sistema según sus responsabilidades y permisos asignados.

## Problema que resuelve
En muchos entornos académicos, la información se maneja de forma manual o dispersa, lo que provoca errores, pérdida de datos y dificultad para generar reportes.  
El SGAB centraliza la información académica, reduce errores humanos y mejora el control y la trazabilidad de los datos.

## Suposiciones iniciales
- El sistema será una aplicación web.
- Los usuarios contarán con acceso a internet.
- El sistema manejará un número limitado de usuarios simultáneos.
- No se contemplan integraciones con sistemas externos en esta versión.
- Se utilizará una base de datos relacional.

## Diagrama de contexto

```
[Usuarios]
|
v
[ Sistema SGAB ]
|
v
[ Base de Datos ]

```