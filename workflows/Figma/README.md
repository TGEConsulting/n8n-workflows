Workflows de Figma

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con Figma, la herramienta de diseno de interfaces colaborativa. El objetivo de este workflow es crear o actualizar automaticamente incidencias en Jira a partir de eventos ocurridos en un archivo de Figma, evitando el registro manual de comentarios o cambios de diseno como tareas de seguimiento.

Estructura

El workflow de esta carpeta sigue un patron de disparador mas manejo de errores. El nodo Figma Trigger escucha eventos en tiempo real (por ejemplo comentarios) mediante un webhook que n8n registra automaticamente en el archivo de Figma al activar el workflow. Los nodos Jira crean o actualizan una incidencia en el proyecto configurado con la informacion del evento recibido. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada ante fallos inesperados.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Figma en el nodo Figma Trigger, indicando el archivo o equipo a monitorear. Paso 3: Configurar las credenciales de Jira y el proyecto donde se crearan o actualizaran las incidencias. Paso 4: Activar el workflow para que n8n registre el webhook correspondiente en Figma. Paso 5: Verificar en el historial de ejecuciones de n8n que los eventos de Figma se reciben y las incidencias se crean o actualizan correctamente en Jira.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
1069_Figma_Stickynote_Update_Triggered.json | Figma Events to Jira Issue | Crea o actualiza una incidencia en Jira a partir de los eventos de un archivo de Figma.
