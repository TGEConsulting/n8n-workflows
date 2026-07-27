Workflows de Calendly

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con Calendly, la plataforma de agendamiento de reuniones. El objetivo de estos workflows es reaccionar a eventos de reserva y cancelacion de citas en Calendly para sincronizar la informacion con CRMs, bases de conocimiento y herramientas de marketing como Notion, HubSpot, Mautic y KlickTipp, evitando el registro manual de cada cita.

Estructura

Todos los workflows de esta carpeta parten de un nodo Calendly Trigger que escucha los eventos de la cuenta de Calendly. Dos de ellos envian la informacion de la nueva reunion directamente a una base de datos de Notion, uno de ellos enriqueciendo previamente el contacto con Dropcontact. Otro workflow crea o actualiza un contacto en Mautic. Uno mas completo utiliza Clearbit para enriquecer el email y la empresa del invitado, filtra las direcciones de correo personales y crea o actualiza la empresa y el contacto o lead correspondiente en HubSpot. Dos workflows procesan tanto reservas como cancelaciones (incluyendo invitados adicionales) y suscriben o actualizan a los contactos en KlickTipp segun el tipo de evento. El ultimo workflow es una plantilla base compuesta unicamente por el disparador de Calendly y un nodo Error Handler (Stop And Error) para depuracion.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow deseado en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Calendly en el nodo Calendly Trigger, indicando el tipo de evento a escuchar (reserva o cancelacion). Paso 3: Configurar las credenciales de la herramienta de destino segun el workflow (Notion, Dropcontact, Mautic, Clearbit, HubSpot o KlickTipp). Paso 4: Ajustar los campos y mapeos de datos (nombre, email, empresa, invitados) segun la estructura de la base o el CRM de destino. Paso 5: Activar el workflow y realizar una reserva de prueba en Calendly para verificar en el historial de ejecuciones de n8n que la informacion se sincroniza correctamente.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0039_Calendly_Notion_Automate_Triggered.json | Calendly to Notion Automation | Registra automaticamente en Notion la informacion de cada nueva reunion agendada en Calendly.
0125_Calendly_Notion_Automate_Triggered.json | Calendly to Notion with Dropcontact Enrichment | Enriquece los datos del invitado con Dropcontact y registra la reunion en una base de datos de Notion.
0277_Calendly_Mautic_Create_Triggered.json | Calendly to Mautic Contact Automation | Crea o actualiza un contacto en Mautic cada vez que se agenda un nuevo evento en Calendly.
0430_Calendly_Filter_Create_Triggered.json | Calendly to HubSpot CRM Enrichment | Filtra correos personales, enriquece el contacto y la empresa con Clearbit y crea o actualiza la empresa, el contacto y el lead en HubSpot.
0660_Calendly_Noop_Create_Triggered.json | Calendly to KlickTipp Booking and Cancellation Automation | Procesa reservas y cancelaciones de Calendly, incluyendo invitados adicionales, y suscribe o actualiza los contactos en KlickTipp.
0661_Calendly_Noop_Create_Triggered.json | Calendly to KlickTipp Booking and Cancellation Automation (variante) | Variante del mismo flujo de sincronizacion de reservas y cancelaciones de Calendly con KlickTipp.
1009_Calendly_Automate_Triggered.json | Calendly Trigger Automation | Plantilla base que escucha los eventos de Calendly y permite disparar acciones posteriores en n8n.
