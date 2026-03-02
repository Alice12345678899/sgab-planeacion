# Especificación de Requisitos – SGAB

## 1. Introducción

El presente documento define los requisitos funcionales y no funcionales del Sistema de Gestión Académica Básico (SGAB).  
Los requisitos constituyen la base para la estimación, el análisis de riesgos y la definición del alcance del proyecto.


---

## 2. Requisitos Funcionales (RF)

Los requisitos funcionales describen lo que el sistema debe hacer.

### RF-01
El sistema debe permitir registrar nuevos alumnos ingresando nombre completo, matrícula única y carrera.

### RF-02
El sistema debe permitir modificar la información de un alumno previamente registrado.

### RF-03
El sistema debe permitir registrar nuevas materias indicando nombre y clave única.

### RF-04
El sistema debe permitir asignar materias a alumnos registrados.

### RF-05
El sistema debe permitir capturar calificaciones numéricas dentro de un rango válido de 0 a 100.

### RF-06
El sistema debe permitir consultar el historial académico completo de un alumno.

### RF-07
El sistema debe permitir generar un reporte básico de calificaciones por alumno en formato digital.

### RF-08
El sistema debe permitir registrar usuarios asignándoles un rol específico (administrativo o docente).

---

## 3. Requisitos No Funcionales (RNF)

Los requisitos no funcionales describen cómo debe comportarse el sistema.

### RNF-01 – Autenticación
El sistema debe requerir autenticación mediante usuario y contraseña antes de permitir el acceso a cualquier funcionalidad.

### RNF-02 – Rendimiento
El sistema debe responder a consultas en un tiempo menor a 2 segundos bajo condiciones normales de operación.

### RNF-03 – Validación de datos
El sistema debe validar que las calificaciones capturadas estén dentro del rango de 0 a 100.

### RNF-04 – Persistencia
El sistema debe almacenar la información de forma persistente en una base de datos relacional.

### RNF-05 – Control de roles
El sistema debe restringir el acceso a funcionalidades según el rol del usuario autenticado.

### RNF-06 – Auditoría
El sistema debe registrar cambios realizados en calificaciones, incluyendo usuario responsable y fecha.

---

## 4. Justificación de Requisitos No Funcionales Clave

### Seguridad (RNF-01 y RNF-05)
La autenticación y el control de roles son esenciales para proteger la confidencialidad e integridad de la información académica.

### Rendimiento (RNF-02)
Un tiempo de respuesta menor a 2 segundos mejora la experiencia del usuario y evita demoras operativas.

### Integridad de datos (RNF-03)
La validación de calificaciones evita errores humanos y mantiene coherencia en la información académica.

### Trazabilidad (RNF-06)
La auditoría permite identificar modificaciones realizadas, reduciendo riesgos organizacionales.

---

## 5. Actores y Casos de Uso

### Actores
- Administrativo
- Docente

### Casos de uso principales

- Registrar alumno
- Registrar materia
- Capturar calificaciones
- Consultar historial académico
- Generar reporte

### Representación simplificada


```
+----------------------------------+
|              SGAB                |
|----------------------------------|
[Administrativo] ---> (Registrar alumno)
[Administrativo] ---> (Registrar materia)
[Administrativo] ---> (Generar reporte)
[Docente] ---------> (Capturar calificaciones)
[Docente] ---------> (Consultar historial)

```

---

## 6. Módulos del Sistema

El sistema se organiza en los siguientes módulos:

1. Módulo de Usuarios
2. Módulo de Alumnos
3. Módulo de Materias
4. Módulo de Calificaciones
5. Módulo de Reportes

La modularización facilita la mantenibilidad, estimación y control del alcance del proyecto.
