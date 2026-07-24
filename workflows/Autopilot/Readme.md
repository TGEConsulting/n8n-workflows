# Workflows de Autopilot

## Objetivo
Esta carpeta agrupa los workflows de n8n que se integran con Autopilot, la plataforma de automatizacion de marketing y gestion de contactos. El objetivo es ejecutar acciones sobre contactos en Autopilot de forma manual y sincronizar los eventos que ocurren en Autopilot con otras herramientas como Airtable.

## Estructura
Se identifican dos patrones: un flujo disparado manualmente que ejecuta varias acciones consecutivas sobre Autopilot (por ejemplo, crear o actualizar contactos y anadirlos a listas o journeys); y un flujo que escucha eventos de Autopilot mediante un disparador propio, transforma los datos recibidos con un nodo Set y los guarda en Airtable. Ambos incluyen un nodo Error Handler (Stop And Error) para detener la ejecucion ante estados inesperados.

## Metodo de aplicacion
Paso 1: Revisar el nombre de cada archivo para identificar si el workflow ejecuta acciones manuales sobre Autopilot o si escucha eventos de Autopilot para sincronizarlos con Airtable.
Paso 2: Importar el archivo JSON elegido en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows.
Paso 3: Configurar las credenciales de Autopilot (API Key) en los nodos Autopilot y Autopilot Trigger, y las credenciales de Airtable en caso de usar ese workflow.
Paso 4: Activar el workflow para que n8n registre el disparador correspondiente en Autopilot, o ejecutar manualmente el flujo de acciones sobre contactos.
Paso 5: Probar generando el evento real en Autopilot o ejecutando el disparador manual, y verificar la ejecucion correcta en el historial de ejecuciones de n8n.

## Workflows incluidos
| Archivo | Nombre del workflow | Descripcion |
|---|---|---|
| 1227_Autopilot_Automate.json | Autopilot Workflow | Flujo disparado manualmente que ejecuta varias acciones consecutivas sobre contactos en Autopilot. |
| 1228_Autopilot_Airtable_Automate_Triggered.json | Autopilottrigger Workflow | Escucha eventos de Autopilot, transforma los datos recibidos y los guarda en Airtable. |
