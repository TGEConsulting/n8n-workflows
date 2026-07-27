Workflows de ConvertKit

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con ConvertKit, la plataforma de email marketing orientada a creadores de contenido. El objetivo de este workflow es reaccionar en tiempo real cuando un nuevo suscriptor se registra a traves de un formulario de ConvertKit, para disparar procesos automatizados dentro de n8n, evitando la revision manual de las nuevas suscripciones.

Estructura

El workflow de esta carpeta sigue un patron de disparador mas manejo de errores. El nodo ConvertKit Trigger escucha en tiempo real la incorporacion de nuevos suscriptores a traves de un formulario, mediante un webhook que n8n registra automaticamente en la cuenta de ConvertKit al activar el workflow. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada si el flujo llega a un estado no esperado, lo que facilita la depuracion durante pruebas.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de ConvertKit (API Key y API Secret) en el nodo ConvertKit Trigger. Paso 3: Seleccionar el formulario especifico de ConvertKit cuyos nuevos suscriptores deben disparar el workflow. Paso 4: Activar el workflow para que n8n registre el webhook correspondiente en ConvertKit. Paso 5: Anadir los nodos posteriores al disparador segun el proceso de negocio que se quiera automatizar y verificar en el historial de ejecuciones de n8n que los nuevos suscriptores se reciben correctamente.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0723_Convertkit_Create_Triggered.json | ConvertKit New Subscriber Automation | Escucha en tiempo real la incorporacion de nuevos suscriptores a traves de un formulario de ConvertKit y permite disparar acciones posteriores en n8n.
