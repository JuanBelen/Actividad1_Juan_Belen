# Actividad 1 - Agente de Ventas con n8n

Workflow de n8n que atiende una conversación de chat, califica al lead y deja registro tanto en una planilla como por correo.

## Cómo funciona

1. **Chat Trigger**: abre una ventana de chat donde el usuario escribe su consulta.
2. **AI Agent** (modo Tools Agent): es el cerebro del flujo. Tiene un system prompt con rol, objetivos y reglas (por ejemplo, no inventar precios y no registrar un lead si falta el email). Corre con un máximo de 7 iteraciones para evitar bucles.
3. **OpenRouter Chat Model**: el modelo de lenguaje que usa el agente para razonar y responder.
4. **Google Sheets (como Tool)**: el agente decide por sí solo cuándo llamarla, cuando detecta que ya tiene nombre y email del lead. Escribe (o actualiza, si el email ya existe) una fila con fecha, nombre, email, empresa, interés y estado.
5. **Gmail**: al terminar la ejecución, envía un correo con el mensaje del usuario y la respuesta del agente, a modo de log para supervisión humana.

## Por qué OpenRouter

Elegí OpenRouter en vez de conectar directo a OpenAI o Anthropic por:

- **Una sola API key** para acceder a modelos de distintos proveedores (OpenAI, Anthropic, Google, Meta, etc.), sin gestionar credenciales separadas por cada uno.
- **Flexibilidad para cambiar de modelo** sin tocar la credencial del workflow, solo el campo de modelo en el nodo.
- **Acceso a modelos gratuitos** para pruebas y desarrollo, útil en esta etapa de aprendizaje sin generar costos.

## Archivo

El workflow exportado está en [`Actividad1_juan_belen.json`](./Actividad1_juan_belen.json), listo para importar en cualquier instancia de n8n.
