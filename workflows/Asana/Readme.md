# Workflows de Asana

## Objetivo
Esta carpeta agrupa los workflows de n8n que se integran con Asana, la herramienta de gestion de proyectos y tareas. El objetivo es reaccionar automaticamente a eventos que ocurren en Asana (creacion o actualizacion de tareas y proyectos) para sincronizar esa informacion con otras herramientas o para exponerla a traves de un webhook propio, reduciendo el trabajo manual de seguimiento.

## Estructura
Se identifican tres patrones distintos: un flujo que combina un disparador de Asana con logica condicional (If) y Notion para sincronizar tareas entre ambas plataformas; un flujo simple de disparador mas manejo de errores que escucha cualquier evento de Asana; y un flujo que expone un webhook propio para crear o actualizar informacion en Asana desde sistemas externos. La mayoria incluye un nodo Error Handler (Stop And Error) para detener la ejecucion ante estados inesperados.

## Metodo de aplicacion
Paso 1: Revisar el nombre de cada archivo para identificar si el workflow escucha eventos de Asana o si expone un webhook para actuar sobre Asana.
Paso 2: Importar el archivo JSON elegido en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows.
Paso 3: Configurar las credenciales de Asana (token de acceso personal o OAuth) en los nodos Asana y Asana Trigger, y las credenciales de Notion en caso de usar ese workflow.
Paso 4: Activar el workflow para que n8n registre el webhook correspondiente en Asana, o publicar la URL del webhook propio si el flujo lo expone.
Paso 5: Probar generando el evento real en Asana (crear o actualizar una tarea) y verificar la ejecucion correcta en el historial de ejecuciones de n8n.

## Workflows incluidos
| Archivo | Nombre del workflow | Descripcion |
|---|---|---|
| 0241_Asana_Notion_Create_Triggered.json | If Workflow | Se dispara con eventos de Asana, aplica logica condicional y sincroniza la informacion de tareas con Notion. |
| 0967_Asana_Update_Triggered.json | Receive updates when an event occurs in Asana | Escucha en tiempo real cualquier evento que ocurra en Asana mediante Asana Trigger y permite disparar acciones posteriores en n8n. |
| 1223_Asana_Webhook_Automate_Webhook.json | Production Workflow | Expone un webhook propio que permite crear o actualizar informacion en Asana desde sistemas externos. |
