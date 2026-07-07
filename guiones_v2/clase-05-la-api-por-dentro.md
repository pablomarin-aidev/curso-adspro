# Clase 5 — La API por dentro (sin tecnicismos)

**Módulo 5 · LA API POR DENTRO · ~9 min**
**Formato:** puros bullets cortos, contenido completo de la clase (alternativa a `guiones/`).

- La app normal obliga a estar tú, celular en mano, respondiendo uno por uno.
- No conecta con tu CRM.
- No lanza campañas.
- No atiende mientras duermes.
- La API es la puerta oficial de Meta para que otros programas hablen con WhatsApp.

## Lo que aprenderás
- Qué es una API y qué permite hacer.
- Cómo viaja un mensaje: número, BSP, CRM, webhooks, ventana de 24h.
- Cómo funcionan las plantillas (HSM).
- Cuánto cobra Meta y qué capacidades avanzadas existen.

## Qué es una API
- API = "interfaz de programación".
- Pensarla como un mesero: pides algo, lo lleva a la cocina de WhatsApp, trae la respuesta.
- App normal = cocinar tú un plato a la vez.
- API = meseros atendiendo cientos de mesas al tiempo.
- No reemplaza WhatsApp, conecta otros sistemas con él.
- Permite:
  - **Mensajes automatizados** — confirmaciones, recordatorios.
  - **Notificaciones** — disparadas por un evento.
  - **Bots y agentes de IA** — responden y agendan sin que estés presente.
  - **Integración** — CRM, web, formularios, anuncios.
  - **Escalabilidad** — de 20 chats a 2.000 sin contratar 20 personas.

## Arquitectura simple
- **Número:** la línea de WhatsApp Business, la cara que ve el cliente.
- **BSP:** proveedor oficial aprobado por Meta, el puente legal y técnico.
- **CRM / plataforma:** donde vive la conversación, el cerebro.
- **Web, formularios, anuncios:** canales de entrada.
- En una frase: el número es la cara, el BSP el puente, el CRM el cerebro.

## Webhooks
- Un webhook es un "aviso automático".
- **Mensaje entrante:** cliente escribe → Meta detecta → dispara webhook → plataforma decide qué hacer.
- **Mensaje saliente:** plataforma pide enviar → API entrega → devuelve estado.
- Sin webhooks no hay tiempo real.

## Ventana de 24 horas, plantillas y permiso
- **Ventana de 24h:** el cliente escribe, se puede responder libremente.
- **Fuera de la ventana:** solo se puede iniciar con plantilla (HSM) aprobada.
- **Opt-in:** el cliente debió aceptar que le escribas.
- Sin permiso, Meta frena.
- Regla: dentro de 24h eres libre; fuera, necesitas plantilla y permiso.

## Plantillas / HSM
- Mensajes prediseñados que Meta revisa y aprueba.
- **Categorías:**
  - **Marketing:** promoción y reactivación.
  - **Utility:** transacciones y servicio.
  - **Authentication:** códigos de verificación.
- **Qué llevan:** variables, botones, carruseles.
- **Por qué las rechazan:**
  - Texto tipo spam.
  - Variables mal armadas.
  - Categoría equivocada.
  - Links sospechosos.

## Cuánto cobra Meta
- Cobra por **conversación**, no por mensaje suelto.
- El precio cambia según categoría y país.
- Rangos: *(a insertar según la fuente del curso)*.
- No es gratis, pero el costo por venta es bajo.

## Capacidades avanzadas
- **WhatsApp Flows:** formularios nativos dentro del chat.
- El cliente agenda o cotiza sin salir de WhatsApp.
- **Catálogo y carrito:** una tiendita dentro del chat.
- Convierten el WhatsApp en un canal de ventas completo.

## Recurso: pasos del setup real
- Business Manager: configurarlo en Meta.
- Verificación del negocio.
- Dar de alta el número.
- Configurar el display name.

## Para recordar
- La app deja hablar; la API deja construir un negocio que vende solo.
- Camino del mensaje: número → BSP → CRM → web/anuncios, con webhooks.
- Dentro de 24h se responde libre; fuera, plantilla y opt-in.
- Meta cobra por conversación y categoría.
- Flows y catálogo convierten el WhatsApp en canal de ventas completo.
