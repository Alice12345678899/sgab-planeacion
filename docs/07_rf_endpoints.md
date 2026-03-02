# Definición de Requisitos Funcionales – Endpoints
Sistema de Gestión Académica Básico (SGAB)

---

## 1. Introducción

En este documento se traducen los requisitos funcionales previamente definidos a endpoints REST.

Se establece la relación:

Requisito Funcional → Método HTTP → Endpoint → Reglas de negocio → Respuesta esperada

El objetivo es definir una base clara para el diseño del backend del sistema SGAB.

---

## 2. Módulo Students (Alumnos)

### RF-01 y RF-02: Gestión de alumnos

### POST /students
Descripción: Registrar un nuevo alumno.

Body esperado:
{
  "matricula": "string",
  "nombre": "string",
  "carrera": "string"
}

Reglas de negocio:
- La matrícula debe ser única.
- Todos los campos son obligatorios.
- El alumno se crea con estatus "active".

Respuesta:
- 201 Created
- 400 Bad Request si faltan datos
- 409 Conflict si la matrícula ya existe

---

### GET /students
Descripción: Obtener listado de alumnos.

Consulta opcional:
GET /students?page=1&limit=10

Respuesta:
{
  "items": [],
  "total": number
}

---

### GET /students/:id
Descripción: Consultar un alumno específico.

Reglas:
- El alumno debe existir.
- Si no existe → 404 Not Found.

---

### PATCH /students/:id
Descripción: Actualizar información del alumno.

Body parcial:
{
  "nombre": "string?",
  "carrera": "string?"
}

Reglas:
- Validar campos modificados.
- Verificar unicidad si cambia matrícula.

---

### DELETE /students/:id
Descripción: Eliminación lógica del alumno.

Regla:
- Cambiar estatus a "inactive".
- Respuesta: 204 No Content.

---

## 3. Módulo Subjects (Materias)

### RF-03: Gestión de materias

### POST /subjects
Crear nueva materia.

Body:
{
  "clave": "string",
  "nombre": "string"
}

Reglas:
- La clave debe ser única.
- Campos obligatorios.

---

### GET /subjects
Listar materias registradas.

---

### GET /subjects/:id
Consultar materia específica.

---

### PATCH /subjects/:id
Actualizar información de la materia.

---

### DELETE /subjects/:id
Eliminar materia (lógica).

---

## 4. Módulo Grades (Calificaciones)

### RF-05, RF-06 y RF-07: Gestión de calificaciones

### POST /grades
Registrar calificación.

Body:
{
  "studentId": "string",
  "subjectId": "string",
  "value": number
}

Reglas:
- El alumno debe existir.
- La materia debe existir.
- value debe estar entre 0 y 100.
- Solo usuarios con rol docente pueden registrar.

Respuesta:
- 201 Created
- 400 si la calificación está fuera de rango
- 404 si alumno o materia no existen

---

### GET /grades
Listar calificaciones.

---

### GET /grades/:id
Consultar calificación específica.

---

### PATCH /grades/:id
Actualizar calificación existente.

Regla:
- Validar nuevamente rango 0–100.

---

### DELETE /grades/:id
Eliminar calificación.

---

## 5. Módulo Users (Usuarios)

### RF-08: Gestión de usuarios

### POST /users
Registrar usuario.

Body:
{
  "nombre": "string",
  "email": "string",
  "password": "string",
  "role": "admin | teacher"
}

Reglas:
- Email único.
- Password obligatoria.
- Role válido.

---

### POST /auth/login
Autenticación de usuario.

Body:
{
  "email": "string",
  "password": "string"
}

Respuesta:
- 200 OK + token
- 401 Unauthorized si credenciales inválidas

---

## Conclusión

Cada requisito funcional del SGAB ha sido traducido a endpoints específicos con su método HTTP correspondiente, reglas de negocio y respuestas esperadas. 

Este documento conecta la especificación de requisitos con el diseño técnico del sistema, manteniendo coherencia con el alcance y los atributos de calidad definidos previamente.