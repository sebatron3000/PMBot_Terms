# Términos de Servicio y Política de Privacidad

**Última actualización:** 27 de agosto de 2026

Al instalar y utilizar la aplicación **"PMBot for Jira"** (en adelante, "la Aplicación") en tu instancia de Atlassian Jira, aceptas los presentes términos. Esta es una herramienta de creación independiente y distribución privada provista "tal cual" (as is) para facilitar la gestión de proyectos.

## 1. Descripción del Servicio
La Aplicación actúa como un puente entre la API de Atlassian Jira y la API de Telegram, permitiendo a los usuarios recibir notificaciones de asignación, reportar avances, visualizar resúmenes ejecutivos y cambiar el estado de las tareas directamente desde un chat de Telegram. La plataforma opera bajo una arquitectura multi-inquilino (multi-tenant), lo que permite a un mismo usuario recibir notificaciones de múltiples proyectos o instancias de Jira en una única cuenta de Telegram.

## 2. Privacidad y Manejo de Datos
Para garantizar un enrutamiento rápido y seguro, PMBot divide el procesamiento de datos entre la infraestructura local de tu empresa y un enrutador centralizado.

### 2.1 Datos almacenados en tu instancia de Jira (Atlassian Forge)
Dentro de la infraestructura segura de tu propia administración en Atlassian, se almacenan:
* Identificadores de usuario de Jira (Account IDs).
* Configuraciones del proyecto (Horarios de reporte, flujos de trabajo lineales y roles asignados).
* El mapeo local de los usuarios con el bot.

### 2.2 Datos procesados por el Enrutador Central (Google Cloud Platform)
Para permitir que un mismo Telegram se conecte a múltiples tableros de Jira, utilizamos Google Cloud Platform (GCP) como un servicio de subprocesamiento (Proxy). En esta base de datos en la nube **solo** se almacena la siguiente información técnica para fines de enrutamiento:
* Tu identificador numérico público de Telegram (Chat ID).
* Un arreglo con las URLs de los webhooks de las instancias de Jira a las que has otorgado permiso de vinculación.
* Tokens temporales de un solo uso para registrar cuentas (los cuales se autodestruyen en 24 horas o al ser utilizados).

### 2.3 Tránsito de Contenido y Mensajes
El contenido de tus tareas (títulos, descripciones, comentarios de avances y nombres de los responsables) viaja de forma encriptada entre Jira, nuestro proxy en GCP y Telegram. **GCP no almacena, registra ni retiene el contenido de tus mensajes ni la información de tus tickets.** El proxy actúa únicamente como un conducto en tiempo real. El desarrollador y creador de la Aplicación **no tiene acceso** a tus tickets de Jira, historial de comentarios, credenciales de usuarios, ni a las conversaciones en Telegram.

## 3. Limitación de Responsabilidad
El uso de la Aplicación es bajo el propio riesgo y responsabilidad del usuario o entidad que la instala. Al no ser un producto comercial público del Atlassian Marketplace, no se ofrecen garantías explícitas de disponibilidad ininterrumpida (SLA), mantenimiento correctivo, ni soporte técnico 24/7. 

* **Dependencia de Terceros:** El funcionamiento continuo de PMBot depende de la estabilidad y disponibilidad de las APIs de Atlassian, Telegram y Google Cloud Platform. PMBot no se hace responsable por retrasos o pérdida de notificaciones derivados de caídas en estos servicios externos.
* **Manejo de Información Sensible:** Dado que la Aplicación transmite resúmenes a través de Telegram (una aplicación de mensajería de terceros), es absoluta responsabilidad del usuario y de la organización administradora de Jira evitar la transmisión de contraseñas, credenciales, datos financieros o información personal altamente confidencial a través de los reportes del bot.

## 4. Desinstalación y Derecho al Olvido
El administrador puede revocar el acceso y desinstalar la Aplicación en cualquier momento desde la configuración de "Manage Apps" en su instancia de Jira, lo cual detendrá el envío de notificaciones desde ese proyecto. 

Para que un usuario elimine completamente su huella digital del enrutador central (GCP), puede solicitar la eliminación de su Chat ID o simplemente bloquear y eliminar la conversación con el bot en la aplicación de Telegram, lo que invalidará cualquier intento de enrutamiento futuro.
