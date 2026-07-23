# Workflows de ActiveCampaign

## Objetivo
Esta carpeta agrupa los workflows de n8n que se integran con ActiveCampaign, la plataforma de automatizacion de marketing y CRM. El objetivo de estos workflows es reaccionar a eventos que ocurren dentro de ActiveCampaign (por ejemplo la creacion de una cuenta) para disparar procesos automatizados dentro de n8n, evitando revisiones manuales del CRM.

## Estructura
El workflow de esta carpeta sigue un patron de disparador mas manejo de errores. El nodo ActiveCampaign Trigger escucha eventos en tiempo real mediante un webhook que n8n registra automaticamente en la cuenta de ActiveCampaign al activar el workflow. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada si el flujo llega a un estado no esperado, lo que facilita la depuracion durante pruebas.

## Metodo de aplicacion
Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows.
Paso 2: Configurar las credenciales de ActiveCampaign (API URL y API Key) en el nodo ActiveCampaign Trigger.
Paso 3: Activar el workflow para que n8n registre el webhook correspondiente en ActiveCampaign.
Paso 4: Sustituir o ampliar los nodos posteriores al disparador segun el proceso de negocio que se quiera automatizar, por ejemplo notificar a un equipo o sincronizar el dato con otra herramienta.
Paso 5: Probar generando el evento real en ActiveCampaign y verificar la ejecucion correcta en el historial de ejecuciones de n8n.

## Workflows incluidos
| Archivo | Nombre del workflow | Descripcion |
|---|---|---|
| 0057_Activecampaign_Create_Triggered.json | Receive updates when a new account is added by an admin in ActiveCampaign | Escucha en tiempo real la creacion de nuevas cuentas por parte de un administrador en ActiveCampaign y permite disparar acciones posteriores en n8n. |
