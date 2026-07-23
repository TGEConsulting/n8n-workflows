# Workflows de Affinity

## Objetivo
Esta carpeta agrupa los workflows de n8n que se integran con Affinity, la plataforma de CRM basada en relaciones utilizada por equipos de inversion, ventas y desarrollo de negocio. El objetivo es reaccionar automaticamente cuando ocurre un evento dentro de Affinity (por ejemplo la creacion de una nueva lista) para disparar procesos posteriores en n8n sin depender de revisiones manuales del CRM.

## Estructura
El workflow de esta carpeta sigue un patron de disparador mas manejo de errores. El nodo Affinity Trigger escucha eventos en tiempo real mediante un webhook que n8n registra automaticamente en la cuenta de Affinity al activar el workflow. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada si el flujo llega a un estado no esperado, lo que facilita la depuracion durante pruebas.

## Metodo de aplicacion
Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows.
Paso 2: Configurar las credenciales de Affinity (API Key) en el nodo Affinity Trigger.
Paso 3: Activar el workflow para que n8n registre el webhook correspondiente en Affinity.
Paso 4: Sustituir o ampliar los nodos posteriores al disparador segun el proceso de negocio que se quiera automatizar, por ejemplo notificar al equipo comercial o sincronizar la lista con otra herramienta.
Paso 5: Probar generando el evento real en Affinity (crear una lista) y verificar la ejecucion correcta en el historial de ejecuciones de n8n.

## Workflows incluidos
| Archivo | Nombre del workflow | Descripcion |
|---|---|---|
| 1085_Affinity_Create_Triggered.json | Receive updates when a new list is created in Affinity | Escucha en tiempo real la creacion de nuevas listas en Affinity mediante el nodo Affinity Trigger y permite disparar acciones posteriores en n8n. |
