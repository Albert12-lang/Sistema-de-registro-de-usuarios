# Sistema-de-registro-de-usuarios
Documentación del sistema de registro de usuarios en github.

Está documentación tendrá

Documento de requerimientos funcionales y no funcionales
* Documento de requerimientos funcionales y no funcionales.
  
* Tabla o plan de pruebas funcionales (mínimo 3 casos de prueba con resultado esperado y validación).
  
* Propuesta de mantenimiento correctivo, adaptativo o perfectivo.

Estilo Markdown
# Sistema de Registro de Usuarios

## Descripción del Caso
El proyecto consiste en el análisis, diagnóstico y propuesta de mantenimiento para un **Sistema de Registro de Usuarios**, el cual permite gestionar la incorporación de nuevos usuarios, validar datos, cifrar contraseñas, enviar correos de confirmación y administrar sesiones con tokens JWT.  
El documento original detalla problemas, tipos de mantenimiento aplicables y mejoras funcionales sugeridas. 

---

## Autores
1. Wellingto Zinedine Alavera Mejía  
2. Diego Hernán Baque Tutiven  
3. Jeremy Alexis Calva Rea  
4. Eduardo Lehilser Encalada Lascano  
5. Francisco Alberto Landivar López  
6. Armando Sebastián Peliza Martínez  

Docente: **Ing. Jorge Dumar Guevara Serrano**  
Asignatura: **Introducción a Ingeniería de Software**  

---

## Objetivos del Proyecto

### Objetivo General
Analizar el sistema actual de registro de usuarios, identificar fallas o áreas de mejora y proponer un tipo de mantenimiento adecuado junto con un cambio funcional que incremente la calidad del software.

### Objetivos Específicos
- Investigar los conceptos teóricos del mantenimiento de software.  
- Analizar el caso y detectar problemas de usabilidad, seguridad y rendimiento.  
- Determinar tipos de mantenimiento aplicables con sustento teórico y técnico.  
- Proponer un cambio funcional que mejore la experiencia del sistema.  
- Redactar un informe técnico con conclusiones y reflexión final.  

---

## Requerimientos del Sistema

### Funcionalidades Principales
- Formulario de registro con validaciones (nombre, correo, contraseña).  
- Validación frontend/backend de integridad de datos.  
- Cifrado de contraseñas con **bcrypt**.  
- Envío de correo de confirmación.  
- Redirección automática al dashboard.  
- Gestión de sesiones mediante **JWT**.  

### Requerimientos No Funcionales
- Documentación técnica clara.  
- Seguridad contra ataques comunes.  
- Escalabilidad en momentos de carga alta.  
- Rendimiento estable incluso con >1000 solicitudes concurrentes.  

---

## Análisis del Problema

### Problemas Identificados

#### Problemas de Usabilidad
- Requisitos complejos de contraseña generan abandono.  
- El correo de confirmación presenta un 30% de fallos.  
- No existen opciones de registro alternativo (Google, Facebook).  
- Interfaz poco optimizada para móviles.  

#### Deficiencias de Seguridad
- No hay protección contra fuerza bruta.  
- No implementa autenticación multifactor.  
- Vulnerabilidad a ataques de timing.  
- No registra intentos fallidos.  

#### Limitaciones Técnicas
- Escalabilidad reducida en la base de datos.  
- Respuesta lenta bajo alta concurrencia (>1000 registros).  
- Acoplamiento elevado entre componentes.  
- Documentación insuficiente.  

---

## Tipos de Mantenimiento Propuestos

### ✔ Correctivo
- Solucionar fallos de verificación de correo.  
- Implementar **rate limiting** para evitar ataques de fuerza bruta.  
- Reparación de bugs en validación e inserción de datos.  

### ✔ Adaptativo
- Integrar autenticación social con OAuth 2.0.  
- Incorporar soporte para GDPR y LGPD.  
- Implementar autenticación biométrica en móviles.  

### ✔ Perfectivo
- Rediseño de interfaz para mejorar experiencia de usuario.  
- Optimización del flujo del registro.  
- Carga progresiva para mejorar percepción de velocidad.  

### ✔ Preventivo
- Migración a microservicios.  
- Logging estructurado.  
- Pruebas automatizadas para reducir regresiones.  

---

## Justificación del Mantenimiento

### Justificación General
- Aumenta la tasa de conversión en un 20%.  
- Reduce la carga del soporte técnico en un 35%.  
- Mejora la retención de usuarios en los primeros 30 días (15%).  

### Justificación Técnica
- Reduce el tiempo de respuesta en un 40%.  
- Incrementa disponibilidad a 99.9%.  
- Permite escalar hasta 10,000 usuarios concurrentes.  
- Disminuye incidentes de seguridad en un 60%.  

---

## Cambio Funcional Propuesto

### **Nombre:** Reportes Automáticos

### **Descripción**
El sistema agregará una función que genere un **reporte automático en PDF** cuando un usuario denuncie a otro. El archivo contendrá información sobre el motivo del reporte y se enviará automáticamente al sistema.  

### **Mejora o Corrección**
- Reduce intervención del área técnica.  
- Previene errores humanos en la documentación de incidentes.  
- Aumenta productividad y eficiencia del sistema.  

### **Cómo se Implementará**
1. Crear una nueva sección de reportes.  
2. Agregar filtros de motivos del reporte.  
3. Implementar exportación automática a PDF.  
4. Crear una interfaz para previsualización del reporte.  
5. Probar validación y exportación del archivo.  
6. Documentar la nueva función y notificar a usuarios.  

### **Impacto**
- **Mantenibilidad:** la función será modular y fácil de extender.  
- **Calidad:** mejora la eficiencia, seguridad y usabilidad.  

---

## Tabla de Pruebas

| ID | Prueba | Descripción | Resultado Esperado | Estado |
|----|--------|-------------|--------------------|--------|
| PR01 | Validación de Datos | Verificar integridad del formulario | Datos válidos y consistentes | Pendiente |
| PR02 | Confirmación de Email | Evaluar tasa de entrega y éxito | Confirmación estable y rápida | Pendiente |
| PR03 | Seguridad | Probar fuerza bruta, timing y MFA | Sistema resistente y protegido | Pendiente |
| PR04 | Rendimiento | Probar carga >1000 registros | Sistema responde sin fallos | Pendiente |
| PR05 | Reportes Automáticos | Validar exportación a PDF | Archivo válido y correcto | Pendiente |
| PR06 | Registro Alternativo | Probar autenticación OAuth | Registro exitoso | Pendiente |

---

## Reflexión sobre el Control de Versiones
El control de versiones es esencial para proyectos en constante evolución como un sistema de registro de usuarios.  
Permite:

- Registrar cambios y retroceder cuando existe un error.  
- Facilitar el trabajo colaborativo entre desarrolladores.  
- Evitar pérdida de código y conflictos entre versiones.  
- Mantener trazabilidad del mantenimiento (correctivo, adaptativo, preventivo, perfectivo).  
- Integrar mejoras graduales sin afectar la estabilidad del sistema.  

Un flujo bien organizado con ramas como **main**, **develop**, **feature/** y **hotfix/** mejora la calidad y mantenibilidad del proyecto.

---

