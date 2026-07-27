Workflows de Discord

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con Discord, la plataforma de mensajeria y comunidades. El objetivo de estos workflows es publicar mensajes programados en canales de Discord y notificar el resultado de la verificacion de correos electronicos enviados mediante un formulario, evitando el envio manual de mensajes y la verificacion manual de contactos.

Estructura

El primer workflow utiliza tres pares de nodos Cron y Discord independientes, cada uno programado para publicar un mensaje en un canal de Discord en un horario distinto. El segundo workflow parte de un n8n Form Trigger que recibe un correo electronico, lo verifica con el nodo Hunter (email verifier) y, mediante un nodo If, registra el resultado en Google Sheets y envia una notificacion por Gmail y por Discord si el correo es valido, o no realiza ninguna accion en caso contrario. Ambos workflows incluyen un nodo Error Handler (Stop And Error) para el manejo de fallos.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow deseado en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales del Webhook o bot de Discord en los nodos correspondientes, indicando el canal de destino. Paso 3: Para el workflow de verificacion de correos, configurar ademas las credenciales de Hunter, Google Sheets y Gmail. Paso 4: Ajustar los horarios de los nodos Cron o el formulario del Form Trigger segun el caso de uso. Paso 5: Activar el workflow y verificar en el historial de ejecuciones de n8n que los mensajes se publican en Discord y que los correos se verifican correctamente.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0360_Discord_Cron_Automation_Scheduled.json | Scheduled Discord Messages | Publica mensajes en canales de Discord en tres horarios programados de forma independiente.
2028_Discord_Hunter_Automate_Triggered.json | Email Verification with Hunter and Discord Notification | Verifica un correo enviado por formulario con Hunter, lo registra en Google Sheets y notifica el resultado por Gmail y Discord.
