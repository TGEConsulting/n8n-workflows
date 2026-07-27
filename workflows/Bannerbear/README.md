Workflows de Bannerbear

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con Bannerbear, la herramienta de generacion automatizada de imagenes y banners. El objetivo de estos workflows es crear banners personalizados a partir de datos enviados mediante un formulario y publicarlos automaticamente en un canal de Discord, evitando el diseno manual de cada imagen.

Estructura

Ambos workflows de esta carpeta parten de un n8n Form Trigger donde el usuario introduce los datos del banner (titulo, ubicacion, fecha e indicaciones para la imagen). Un nodo HTTP Request sube la imagen de referencia a Cloudinary y un nodo Generate AI Banner Image utiliza OpenAI para crear la imagen de fondo a partir del prompt indicado. El nodo Set Parameters organiza los valores (template_id, title, location, date, image_prompt) y el nodo Bannerbear (Send to Bannerbear Template) genera el banner final combinando los placeholders de imagen, texto, ubicacion y fecha. Un nodo HTTP Request adicional descarga el banner generado y un nodo Discord lo publica en el canal configurado. Varios nodos Sticky Note documentan cada seccion del flujo dentro del propio editor.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Cloudinary API para la subida de imagenes. Paso 3: Configurar las credenciales de OpenAI para la generacion de la imagen del banner. Paso 4: Configurar las credenciales de Bannerbear, indicando el template_id de la plantilla que se desea usar. Paso 5: Configurar las credenciales del bot de Discord y el canal de destino. Paso 6: Activar el workflow, completar el formulario generado por el n8n Form Trigger y verificar en el historial de ejecuciones de n8n que el banner se genera y se publica correctamente en Discord.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0525_Bannerbear_Discord_Create_Webhook.json | Form to Bannerbear to Discord Automation | Recibe datos desde un formulario, genera una imagen con OpenAI, crea un banner en Bannerbear y lo publica en Discord.
1665_Bannerbear_Discord_Automation_Webhook.json | Form to Bannerbear to Discord Automation (variante) | Variante del mismo flujo de creacion de banners con Bannerbear y publicacion automatica en Discord.
