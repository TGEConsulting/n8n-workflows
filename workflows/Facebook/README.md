Workflows de Facebook

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con Facebook, la red social y plataforma de paginas empresariales. El objetivo de este workflow es reaccionar a eventos que ocurren en una pagina de Facebook y notificarlos automaticamente en un canal de Mattermost, evitando la revision manual de la actividad de la pagina.

Estructura

El workflow de esta carpeta sigue un patron de disparador mas manejo de errores. El nodo Facebook Trigger escucha eventos en tiempo real mediante un webhook que n8n registra automaticamente en la pagina de Facebook al activar el workflow. El nodo Mattermost publica una notificacion en el canal configurado con la informacion del evento recibido. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada si el flujo llega a un estado no esperado.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Facebook en el nodo Facebook Trigger, indicando la pagina y los eventos a escuchar. Paso 3: Configurar las credenciales de Mattermost y el canal donde se publicaran las notificaciones. Paso 4: Activar el workflow para que n8n registre el webhook correspondiente en Facebook. Paso 5: Verificar en el historial de ejecuciones de n8n que los eventos de Facebook se reciben y se publican correctamente en Mattermost.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0123_Facebook_Mattermost_Update_Triggered.json | Facebook Events to Mattermost Notification | Escucha en tiempo real los eventos de una pagina de Facebook y los notifica en un canal de Mattermost.
