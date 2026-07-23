# Workflows de Airtop Tool (agente web con IA)

## Objetivo
Esta carpeta agrupa workflows de n8n que utilizan Airtop, una herramienta que permite a un Agente de IA controlar un navegador web real (por ejemplo para iniciar sesion, navegar paginas y extraer informacion) como parte de su razonamiento. El objetivo es automatizar tareas que requieren interactuar con sitios web que no ofrecen una API tradicional, delegando esa interaccion a un agente de IA.

## Estructura
El flujo se inicia con un disparador de formulario (Form Trigger) o mediante la ejecucion de otro workflow (Execute Workflow Trigger). Un Agente de IA utiliza el nodo Airtop Tool (apoyado en el nodo base Airtop) para navegar y operar un sitio web segun instrucciones, y el resultado se envia como notificacion a Slack. Incluye nodos Sticky Note para documentacion visual y un nodo Error Handler (Stop And Error) para detener la ejecucion ante estados inesperados.

## Metodo de aplicacion
Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows.
Paso 2: Configurar las credenciales de Airtop (API Key del servicio) en los nodos Airtop y Airtop Tool.
Paso 3: Configurar las credenciales del modelo de lenguaje que utilice el Agente de IA y las credenciales de Slack para las notificaciones de salida.
Paso 4: Adaptar el formulario de entrada (Form Trigger) y las instrucciones del agente segun el sitio web y la tarea que se desea automatizar.
Paso 5: Activar el workflow y probarlo enviando una solicitud a traves del formulario, verificando en el historial de ejecuciones de n8n que el agente complete la navegacion y que Slack reciba la notificacion.

## Workflows incluidos
| Archivo | Nombre del workflow | Descripcion |
|---|---|---|
| 1681_Airtoptool_Slack_Automation_Triggered.json | Airtop Web Agent | Recibe una solicitud por formulario, un Agente de IA usa Airtop Tool para navegar y operar un sitio web, y el resultado se notifica por Slack. |
