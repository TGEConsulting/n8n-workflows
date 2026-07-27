Workflows de Compression

Objetivo

Esta carpeta agrupa los workflows de n8n que utilizan el nodo Compression para descomprimir archivos como parte de una demostracion de agente de IA con acceso a una base de datos SQL. El objetivo de estos workflows es descargar un archivo ZIP de ejemplo, extraer la base de datos SQLite que contiene y permitir que un agente conversacional de OpenAI responda preguntas sobre esos datos.

Estructura

Ambos workflows de esta carpeta siguen la misma estructura. Un Manual Trigger descarga mediante HTTP Request el archivo comprimido chinook.zip, un ejemplo clasico de base de datos de musica. El nodo Compression (Extract zip file) descomprime el archivo y un nodo Read/Write File guarda la base de datos chinook.db de forma local para despues cargarla nuevamente. Un Chat Trigger recibe las preguntas del usuario, las combina con el archivo binario de la base de datos y las envia a un AI Agent (SQL agent with memory) que usa un modelo de OpenAI Chat Model y un Window Buffer Memory para mantener el contexto de la conversacion y responder consultas sobre la base de datos.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de OpenAI para los nodos AI Agent y OpenAI Chat Model. Paso 3: Ejecutar manualmente el flujo de preparacion para descargar y descomprimir el archivo chinook.zip y generar el archivo chinook.db local. Paso 4: Activar el Chat Trigger para habilitar la interfaz de chat del agente. Paso 5: Realizar una pregunta de prueba sobre la base de datos y verificar en el historial de ejecuciones de n8n que el agente responde correctamente usando los datos extraidos.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
1294_Compression_Manual_Automation_Webhook.json | SQL Agent with Sample Database | Descarga y descomprime una base de datos SQLite de ejemplo y permite consultarla mediante un agente de IA conversacional.
1683_Compression_Manual_Automation_Webhook.json | SQL Agent with Sample Database (variante) | Variante del mismo flujo de descompresion de base de datos y consulta mediante agente de IA.
