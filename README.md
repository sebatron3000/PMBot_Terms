# Términos de Servicio y Política de Privacidad

**Última actualización:** 26 de julio de 2026

Al instalar y utilizar la aplicación **"PMBot for Jira"** (en adelante, "la Aplicación") en tu instancia de Atlassian Jira, aceptas los presentes términos. Esta es una herramienta de creación independiente y distribución privada provista "tal cual" (as is) para facilitar la gestión de proyectos.

## 1. Descripción del Servicio
La Aplicación actúa como un puente entre la API de Atlassian Jira y la API de Telegram, permitiendo a los usuarios recibir notificaciones de asignación, reportar avances y cambiar el estado de las tareas directamente desde un chat de Telegram.

## 2. Privacidad y Manejo de Datos
La Aplicación está construida sobre la infraestructura oficial de Atlassian Forge. Para funcionar, almacena de forma encriptada y aislada en tu propia instancia de Jira (mediante Forge Storage - KVS) los siguientes datos técnicos:
* Identificadores de usuario de Jira (Account IDs).
* Identificadores de chat de Telegram (Chat IDs).
* Tokens de acceso de bots de Telegram proporcionados voluntariamente por el administrador.

**Importante:** El creador y desarrollador de la Aplicación **no tiene acceso** a tus tickets de Jira, historial de comentarios, credenciales de usuarios, ni a los mensajes intercambiados en Telegram. Todos los datos residen en la infraestructura segura de Atlassian controlada por tu administración.

## 3. Limitación de Responsabilidad
El uso de la Aplicación es bajo el propio riesgo y responsabilidad del usuario o entidad que la instala. Al no ser un producto comercial público del Atlassian Marketplace, no se ofrecen garantías explícitas de disponibilidad ininterrumpida (SLA), mantenimiento correctivo, ni soporte técnico 24/7. 

## 4. Desinstalación y Revocación
El administrador puede revocar el acceso y desinstalar la Aplicación en cualquier momento desde la configuración de "Manage Apps" en su instancia de Jira. La desinstalación detendrá inmediatamente cualquier sincronización de datos con Telegram.
