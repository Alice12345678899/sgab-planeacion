# Definición del Alcance

## Funcionalidades incluidas
- Gestión de usuarios
- Registro de alumnos
- Registro de materias
- Captura de calificaciones
- Generación de reportes básicos

## Funcionalidades excluidas
- Pagos en línea
- Integraciones con sistemas externos
- Aplicaciones móviles
- Notificaciones automáticas

## Suposiciones
- El sistema se utilizará en un entorno académico controlado.
- No se requiere escalabilidad para grandes volúmenes de usuarios.
- El sistema no evolucionará más allá del periodo académico actual.

## Ejemplo de cambio y su impacto
**Cambio propuesto:** agregar el cálculo de promedios semestrales.  
**Impacto:** incremento en la lógica de negocio, nuevas pruebas y ajuste en la estimación de esfuerzo.

## Ejemplo de scope creep
Solicitudes como “solo agregar exportar a Excel” o “que también envíe correos” pueden parecer pequeñas, pero acumuladas generan retrasos, aumento de riesgos y pérdida de control del proyecto.
