Workflows de Bitly

Objetivo

Esta carpeta agrupa un workflow de n8n que incorpora Bitly, el servicio de acortamiento y gestion de enlaces, dentro de una plantilla mas amplia de agente de IA con acceso a numerosas herramientas y aplicaciones externas. El objetivo es permitir que un asistente conversacional acorte, actualice y gestione enlaces mediante Bitly, ademas de disponer de utilidades de fecha y hora, dentro de un mismo flujo disparado por Webhook.

Estructura

El workflow parte de un nodo Webhook que recibe las solicitudes entrantes y las dirige hacia un AI Agent basado en OpenAI, capaz de razonar y elegir entre un amplio conjunto de herramientas conectadas (entre ellas Bitly App para gestionar enlaces cortos y un nodo Date & Time para calculos temporales). Ademas del nucleo Bitly y Webhook, la plantilla incluye docenas de nodos adicionales de aplicaciones como Gmail, Google Calendar, Google Sheets, Google Docs, Dropbox, Reddit, YouTube, Pushbullet, Perplexity y ElevenLabs, junto con componentes de memoria, extraccion de informacion, analisis de sentimiento y almacenes vectoriales, que actuan como piezas disponibles para ampliar las capacidades del agente segun sea necesario.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Bitly App para permitir la creacion y actualizacion de enlaces cortos. Paso 3: Configurar las credenciales de OpenAI para el nodo AI Agent y activar unicamente las herramientas adicionales que se necesiten para el caso de uso (el resto puede eliminarse o dejarse deshabilitado). Paso 4: Activar el workflow para que n8n exponga la URL del Webhook que recibira las solicitudes. Paso 5: Enviar una solicitud de prueba al Webhook y verificar en el historial de ejecuciones de n8n que el agente utiliza Bitly y las demas herramientas correctamente.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0910_Bitly_Datetime_Update_Webhook.json | AI Agent con Bitly y utilidades de fecha | Agente de IA disparado por Webhook que gestiona enlaces con Bitly, procesa fechas y cuenta con un amplio catalogo de herramientas adicionales.
