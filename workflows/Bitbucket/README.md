Workflows de Bitbucket

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con Bitbucket, la plataforma de alojamiento de repositorios Git de Atlassian. El objetivo de este workflow es reaccionar a eventos que ocurren dentro de un repositorio de Bitbucket para disparar procesos automatizados dentro de n8n, evitando la revision manual de la actividad del repositorio.

Estructura

El workflow de esta carpeta sigue un patron de disparador mas manejo de errores. El nodo Bitbucket Trigger escucha eventos en tiempo real mediante un webhook que n8n registra automaticamente en el repositorio de Bitbucket al activar el workflow. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada si el flujo llega a un estado no esperado, lo que facilita la depuracion durante pruebas.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Bitbucket en el nodo Bitbucket Trigger, indicando el workspace y el repositorio a monitorear. Paso 3: Seleccionar los eventos del repositorio que deben disparar el workflow (por ejemplo push, pull request o comentarios). Paso 4: Activar el workflow para que n8n registre el webhook correspondiente en Bitbucket. Paso 5: Anadir los nodos posteriores al disparador segun el proceso de negocio que se quiera automatizar y verificar en el historial de ejecuciones de n8n que los eventos se reciben correctamente.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0999_Bitbucket_Automate_Triggered.json | Bitbucket Trigger Automation | Escucha en tiempo real los eventos de un repositorio de Bitbucket y permite disparar acciones posteriores en n8n.
