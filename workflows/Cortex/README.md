Workflows de Cortex

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con Cortex, el motor de analisis de observables para respuesta a incidentes de seguridad, en conjunto con TheHive. El objetivo de este workflow es automatizar el analisis de correos electronicos sospechosos: crear un caso en TheHive, extraer los observables (remitente, direcciones IP y dominios) y analizarlos con distintos analizadores de Cortex para apoyar a un equipo de seguridad (SOC) en la investigacion de amenazas.

Estructura

El workflow de esta carpeta parte de un Manual Trigger que lee un correo mediante IMAP Email. Con los datos del correo se crea un caso en TheHive y se anaden observables asociados (email, IP, dominio). El nodo Cortex ejecuta el analizador de reputacion de email, y un nodo If determina el tipo de observable para dirigirlo a los analizadores correspondientes (Email Reputation, OTX IP u OTX Domain). Un nodo Wait dosifica las llamadas a los analizadores, y finalmente los nodos TheHive actualizan el caso con los resultados del analisis para cada tipo de observable (dominio, email o IP).

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de la cuenta IMAP desde la que se leeran los correos a analizar. Paso 3: Configurar las credenciales de TheHive, indicando la plantilla de caso que se debe usar. Paso 4: Configurar las credenciales de Cortex y verificar que los analizadores (Email Reputation, OTX IP, OTX Domain) esten disponibles en la instancia. Paso 5: Ejecutar el workflow con un correo de prueba y verificar en el historial de ejecuciones de n8n que el caso se crea en TheHive y se actualiza con los resultados de los analizadores de Cortex.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0972_Cortex_Emailreadimap_Send.json | Email Threat Analysis with TheHive and Cortex | Crea un caso en TheHive a partir de un correo, extrae sus observables y los analiza con los analizadores de Cortex.
