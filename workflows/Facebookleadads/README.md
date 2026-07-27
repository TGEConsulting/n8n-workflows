Workflows de Facebook Lead Ads

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con Facebook Lead Ads, el formato de anuncios de Facebook para captura de clientes potenciales. El objetivo de este workflow es incorporar automaticamente a KlickTipp, la plataforma de email marketing, cada nuevo lead generado a traves de un anuncio de Facebook, evitando la carga manual de contactos.

Estructura

El workflow de esta carpeta sigue un patron de disparador mas manejo de errores. El nodo Facebook Lead Ads Trigger escucha en tiempo real la creacion de nuevos leads en el formulario de anuncios configurado, mediante un webhook que n8n registra automaticamente al activar el workflow. El nodo KlickTipp suscribe al nuevo lead en la lista o etiqueta correspondiente. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada ante fallos inesperados.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Facebook en el nodo Facebook Lead Ads Trigger, indicando la pagina y el formulario de anuncios a monitorear. Paso 3: Configurar las credenciales de KlickTipp y la etiqueta o lista a la que se debe suscribir al nuevo lead. Paso 4: Activar el workflow para que n8n registre el webhook correspondiente en Facebook. Paso 5: Verificar en el historial de ejecuciones de n8n que los nuevos leads se reciben y se suscriben correctamente en KlickTipp.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0896_Facebookleadads_Stickynote_Automate_Triggered.json | Facebook Lead Ads to KlickTipp | Suscribe automaticamente en KlickTipp cada nuevo lead generado por un formulario de Facebook Lead Ads.
