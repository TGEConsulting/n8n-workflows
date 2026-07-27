Workflows de Deep (Investigacion y Orquestacion con IA)

Objetivo

Esta carpeta agrupa workflows avanzados de n8n que combinan multiples modelos de lenguaje y agentes de IA para tareas complejas de investigacion y generacion de contenido. El objetivo es automatizar la elaboracion de informes de investigacion profunda a partir de una consulta, y la redaccion colaborativa de manuales o documentos mediante varios agentes de IA que se revisan entre si antes de una revision humana final.

Estructura

El primer workflow recibe una solicitud por Telegram o Webhook, realiza busquedas en Google, consulta modelos de lenguaje a traves de OpenRouter para sintetizar la informacion encontrada, agrega y da formato al contenido en Markdown, y guarda el informe final en una base de datos de Notion, respondiendo tambien al Webhook de origen. El segundo workflow implementa una orquestacion multiagente con GPT-4o: un Webhook o disparador inicial guarda la solicitud en Postgres, un Switch dirige la tarea a distintos agentes de OpenAI especializados (cada uno con su propia funcion dentro del proceso de redaccion), los resultados se combinan mediante nodos Function, y finalmente se envia un correo de revision humana con un nodo Wait para pausar el flujo hasta recibir la aprobacion.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow deseado en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de OpenRouter u OpenAI segun el workflow, asi como las de Google Search, Telegram o Notion para el primero, y las de Postgres y correo electronico para el segundo. Paso 3: Ajustar los prompts de cada agente segun el tipo de informe o manual que se desea generar. Paso 4: Enviar una consulta de prueba por Telegram o Webhook, o iniciar el proceso de generacion del manual colaborativo. Paso 5: Verificar en el historial de ejecuciones de n8n que el informe se genera y se guarda correctamente en Notion, o que el manual se completa tras la revision humana.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
2054_Deep_Research_Report_Generation_With_Open_Router_Google_Search_Webhook_Telegram_and_Notion.json | Deep Research Report Generation | Genera informes de investigacion profunda combinando busqueda en Google, modelos de OpenRouter y almacenamiento en Notion, disparado por Telegram o Webhook.
generate-collaborative-handbooks-with-gpt4o-multi-agent-orchestration-human-review.json | Collaborative Handbook Generation with Multi-Agent Review | Orquesta varios agentes de GPT-4o para redactar de forma colaborativa un manual, incorporando una etapa de revision humana antes de finalizarlo.
