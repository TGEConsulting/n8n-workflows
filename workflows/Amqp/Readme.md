# Workflows de AMQP

## Objetivo
Esta carpeta agrupa el workflow de n8n que se integra con colas de mensajeria mediante el protocolo AMQP (Advanced Message Queuing Protocol), por ejemplo colas de ActiveMQ o RabbitMQ. El objetivo es que n8n reciba automaticamente los mensajes publicados en una cola especifica para procesarlos dentro de un flujo de trabajo, sin depender de consultas manuales o sondeo periodico.

## Estructura
El workflow de esta carpeta sigue un patron de disparador mas manejo de errores. El nodo AMQP Trigger se conecta de forma persistente a un servidor de mensajeria y escucha nuevos mensajes en la cola configurada, iniciando la ejecucion del workflow cada vez que llega uno. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada si el flujo llega a un estado no esperado, lo que facilita la depuracion durante pruebas.

## Metodo de aplicacion
Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows.
Paso 2: Configurar las credenciales de conexion AMQP (host, puerto, usuario y contrasena del servidor de mensajeria) en el nodo AMQP Trigger.
Paso 3: Especificar el nombre de la cola que se desea escuchar dentro de la configuracion del nodo.
Paso 4: Activar el workflow para que n8n mantenga la conexion abierta y reciba los mensajes de la cola en tiempo real.
Paso 5: Sustituir o ampliar los nodos posteriores al disparador segun el proceso de negocio que se quiera automatizar con cada mensaje recibido, y probar publicando un mensaje de prueba en la cola.

## Workflows incluidos
| Archivo | Nombre del workflow | Descripcion |
|---|---|---|
| 0138_Amqp_Send_Triggered.json | Receive messages for an ActiveMQ queue via AMQP Trigger | Escucha en tiempo real los mensajes publicados en una cola de ActiveMQ mediante el protocolo AMQP y permite disparar acciones posteriores en n8n. |
