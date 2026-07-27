Workflows de ClickUp

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con ClickUp, la plataforma de gestion de proyectos y tareas. El objetivo de estos workflows es reaccionar a eventos de ClickUp, sincronizar el estado de las tareas con Notion en ambas direcciones y permitir la creacion de tareas desde comandos de Slack, evitando la gestion manual entre estas herramientas.

Estructura

El primer workflow sigue un patron simple de disparador mas manejo de errores: el nodo ClickUp Trigger escucha eventos en tiempo real mediante un webhook registrado automaticamente por n8n. El segundo workflow implementa una sincronizacion bidireccional entre ClickUp y Notion: cuando se actualiza una pagina en una base de datos de Notion se actualiza la tarea correspondiente en ClickUp, y cuando cambia el estado de una tarea en ClickUp se busca la pagina asociada en Notion por su ID de ClickUp y se actualiza su estado. El tercer workflow recibe un comando de Slack mediante un Webhook, extrae el canal, el comando, el usuario y el texto, crea una nueva tarea en ClickUp con ese contenido y responde al Webhook para confirmar la accion en Slack.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow deseado en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de ClickUp en los nodos correspondientes (ClickUp Trigger o ClickUp). Paso 3: Para el workflow de sincronizacion, configurar tambien las credenciales de Notion Trigger y Notion, indicando la base de datos y el campo que almacena el ID de ClickUp. Paso 4: Para el workflow de Slack, configurar el comando de barra diagonal en Slack para que apunte a la URL del Webhook generada por n8n. Paso 5: Activar el workflow y probar el evento correspondiente (actualizacion de tarea, cambio de estado o comando de Slack) verificando en el historial de ejecuciones de n8n que la accion se completa correctamente.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0047_Clickup_Update_Triggered.json | ClickUp Events Automation | Escucha en tiempo real los eventos de una cuenta de ClickUp y permite disparar acciones posteriores en n8n.
0282_Clickup_Notion_Update_Triggered.json | ClickUp and Notion Status Sync | Sincroniza en ambas direcciones el estado de las tareas entre ClickUp y una base de datos de Notion.
0469_Clickup_Respondtowebhook_Create_Webhook.json | Slack Command to ClickUp Task | Crea una tarea en ClickUp a partir de un comando de barra diagonal enviado desde Slack y responde al Webhook.
