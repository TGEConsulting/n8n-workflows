Workflows de Debug Helper

Objetivo

Esta carpeta agrupa un workflow de n8n de caracter educativo que utiliza el nodo Debug Helper como parte de un tutorial para construir un servidor MCP (Model Context Protocol) propio dentro de n8n. El objetivo es mostrar como exponer un conjunto de funciones (herramientas) a un agente de IA conversacional, incluyendo la gestion de eventos de Google Calendar y utilidades de ejemplo como conversion de texto, generacion de datos aleatorios y obtencion de chistes.

Estructura

El workflow se dispara con un Chat Trigger que recibe los mensajes del usuario y los envia a un AI Agent con memoria simple (Simple Memory) y un modelo OpenAI 4o. El agente tiene acceso a un servidor MCP (Google Calendar MCP) con funciones para buscar, crear, actualizar y eliminar eventos de Google Calendar, ademas de un segundo servidor de funciones propio (My Functions Server) que incluye un Switch para enrutar segun el nombre de la funcion solicitada: conversion de texto a mayusculas o minusculas, generacion de datos aleatorios de usuario y obtencion de chistes aleatorios mediante HTTP Request. El nodo Debug Helper se utiliza como herramienta de prueba dentro de este entorno de aprendizaje.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de OpenAI para el nodo AI Agent y de Google Calendar para las funciones de eventos. Paso 3: Revisar la configuracion de los servidores MCP y las funciones expuestas (My Functions Server) para entender como se enrutan las solicitudes segun el nombre de la funcion. Paso 4: Activar el Chat Trigger y probar el asistente solicitando alguna de las funciones disponibles (crear un evento, convertir texto o pedir un chiste). Paso 5: Verificar en el historial de ejecuciones de n8n que el agente invoca correctamente las herramientas del servidor MCP.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
1184_Debughelper_HTTP_Create_Webhook.json | Build Your First AI MCP Server | Tutorial que expone funciones de Google Calendar y utilidades de ejemplo como herramientas MCP para un agente de IA conversacional.
