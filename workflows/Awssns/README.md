Workflows de AWS SNS

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con AWS SNS (Simple Notification Service), el servicio de mensajeria y notificaciones de Amazon Web Services. El objetivo de este workflow es reaccionar en tiempo real a los mensajes publicados en un topico de SNS para disparar procesos automatizados dentro de n8n, evitando la revision manual de las notificaciones.

Estructura

El workflow de esta carpeta sigue un patron de disparador mas manejo de errores. El nodo AWS-SNS-Trigger escucha mensajes entrantes de un topico de AWS SNS mediante un endpoint que n8n suscribe automaticamente al activar el workflow. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada si el flujo llega a un estado no esperado, lo que facilita la depuracion durante pruebas.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de AWS (Access Key y Secret Key) en el nodo AWS-SNS-Trigger. Paso 3: Seleccionar o crear el topico de SNS al que se desea suscribir el trigger. Paso 4: Activar el workflow para que n8n registre la suscripcion correspondiente en AWS SNS. Paso 5: Anadir los nodos posteriores al disparador segun el proceso de negocio que se quiera automatizar y verificar en el historial de ejecuciones de n8n que las notificaciones se reciben correctamente.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0984_Awssns_Automate_Triggered.json | AWS SNS Trigger Automation | Escucha en tiempo real los mensajes publicados en un topico de AWS SNS y permite disparar acciones posteriores en n8n.
