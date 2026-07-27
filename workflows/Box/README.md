Workflows de Box

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con Box, la plataforma de almacenamiento y colaboracion de archivos en la nube. El objetivo de este workflow es reaccionar a eventos que ocurren dentro de una cuenta de Box para disparar procesos automatizados dentro de n8n, evitando la revision manual de la actividad de archivos y carpetas.

Estructura

El workflow de esta carpeta sigue un patron de disparador mas manejo de errores. El nodo Box Trigger escucha eventos en tiempo real mediante un webhook que n8n registra automaticamente en la cuenta de Box al activar el workflow. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada si el flujo llega a un estado no esperado, lo que facilita la depuracion durante pruebas.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Box en el nodo Box Trigger. Paso 3: Seleccionar los eventos de Box que deben disparar el workflow (por ejemplo subida de archivos, cambios de carpeta o comentarios). Paso 4: Activar el workflow para que n8n registre el webhook correspondiente en Box. Paso 5: Anadir los nodos posteriores al disparador segun el proceso de negocio que se quiera automatizar y verificar en el historial de ejecuciones de n8n que los eventos se reciben correctamente.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
1031_Box_Automate_Triggered.json | Box Trigger Automation | Escucha en tiempo real los eventos de una cuenta de Box y permite disparar acciones posteriores en n8n.
