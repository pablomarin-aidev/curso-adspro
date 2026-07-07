# Clase 5 — La API por dentro (sin tecnicismos)

**Módulo 5 · LA API POR DENTRO · ~9 min**
**Formato:** puros bullets, contenido completo de la clase (alternativa a `guiones/`).

- La app normal de WhatsApp obliga a estar tú, con el celular en la mano, respondiendo uno por uno.
- No conecta con tu CRM, no lanza campañas, no atiende mientras duermes.
- La API es la puerta oficial de Meta para que otros programas hablen con WhatsApp por ti.

## Lo que aprenderás
- Qué es una API y qué permite hacer que la app normal no puede.
- Cómo viaja un mensaje por dentro: número, BSP, CRM, webhooks y la ventana de 24 horas.
- Cómo funcionan las plantillas (HSM), cuánto cobra Meta y qué capacidades avanzadas existen.

## Qué es una API (y qué permite hacer)
- API = "interfaz de programación" — pensarla como un mesero: tú/tu CRM/tu bot piden algo, el mesero lo lleva a la cocina de WhatsApp y trae la respuesta.
- App normal = cocinar tú mismo un plato a la vez. API = meseros atendiendo cientos de mesas al tiempo.
- La API no reemplaza WhatsApp: es la conexión oficial para que otros sistemas trabajen con él. Permite:
  - **Mensajes automatizados** — confirmaciones, recordatorios, seguimientos que salen solos.
  - **Notificaciones** — "tu pedido va en camino", "tu cita es mañana", disparadas por un evento.
  - **Bots y agentes de IA** — responden, califican y agendan sin que estés presente.
  - **Integración con el ecosistema** — CRM, web, formularios, anuncios de Meta.
  - **Escalabilidad** — pasar de 20 chats a 2.000 sin contratar 20 personas.

## Arquitectura simple: cómo se conecta todo
- **Número:** la línea de WhatsApp Business — la cara que ve el cliente.
- **BSP:** Business Solution Provider, proveedor oficial aprobado por Meta — el puente legal y técnico hacia la API.
- **CRM / plataforma:** donde vive la conversación, el contacto y la automatización — el cerebro.
- **Web, formularios y anuncios:** canales de entrada que empujan gente hacia el número.
- En una frase: el número es la cara, el BSP es el puente, el CRM es el cerebro.

## Webhooks: cómo entra y sale un mensaje
- Un webhook es un "aviso automático" — cada vez que pasa algo en WhatsApp, Meta le avisa al sistema.
- **Mensaje entrante:** cliente escribe → Meta lo detecta → dispara webhook → la plataforma lo recibe al instante y decide qué hacer.
- **Mensaje saliente:** la plataforma pide a la API que envíe → la API entrega → devuelve estado (entregado, leído o falló).
- Sin webhooks no hay tiempo real. Con ellos, el negocio "escucha" WhatsApp las 24 horas.

## La ventana de 24 horas, las plantillas y el permiso
- **Ventana de 24 horas:** cuando el cliente escribe, se abre una ventana de 24h para responder libremente con cualquier texto.
- **Fuera de la ventana:** ya no se puede escribir texto libre — solo iniciar con una **plantilla (HSM)** aprobada por Meta.
- **Opt-in (permiso):** el cliente debió aceptar que le escribas; sin permiso, Meta frena y el número queda sano.
- Regla: dentro de las 24h eres libre; fuera de ellas, necesitas plantilla y permiso.

## Plantillas / HSM por dentro
- Son mensajes prediseñados que Meta revisa y aprueba antes de usarse para iniciar conversación.
- **Categorías:**
  - **Marketing:** promoción y reactivación — ofertas, novedades, "vuelve con nosotros".
  - **Utility (utilidad):** transacciones y servicio — confirmación de pedido, recordatorio de cita.
  - **Authentication (autenticación):** seguridad — códigos de verificación, OTP.
- **Qué llevan por dentro:** variables (nombre, número de pedido, fecha), botones (CTA o respuestas rápidas), carruseles (varios productos en un mensaje).
- **Por qué las rechazan:** texto tipo spam o con promesas exageradas; variables mal armadas o vacías; categoría equivocada (marketing disfrazado de utility); links sospechosos o sin contexto.
- Si rechazan una plantilla, toca corregirla y reenviarla a revisión.

## Cuánto cobra Meta
- Ya no cobra por mensaje suelto: cobra por **conversación** dentro de una ventana.
- El precio cambia según la **categoría** (marketing suele costar más que utility o servicio) y según el **país**.
- Rangos y tarifas: *(valores a insertar según la fuente del curso)*.
- No es "gratis mandar WhatsApp", pero bien usado el costo por venta es muy bajo frente a otros canales.

## Capacidades avanzadas
- **WhatsApp Flows:** formularios nativos dentro del chat — el cliente agenda, cotiza o elige opciones sin salir de WhatsApp. Menos fricción, más conversión.
- **Catálogo y carrito:** el cliente arma su pedido sin abandonar la conversación — una tiendita dentro del chat.
- Juntas convierten el WhatsApp de canal de mensajes a canal de ventas completo.

## Recurso: pasos del setup real (en orden)
- Business Manager: entrar y configurar el Business Manager de Meta.
- Verificación: completar la verificación del negocio.
- Número: dar de alta el número que usará la API.
- Display name: configurar el nombre que verá el cliente.
- Con esto listo, el número queda conectado y empieza a recibir mensajes por webhook.

## Para recordar
- La app deja hablar; la API deja construir un negocio que vende solo.
- Camino del mensaje: número → BSP → CRM → web/formularios/anuncios, con webhooks en tiempo real.
- Dentro de las 24h se responde libre; fuera, necesita plantilla (HSM) aprobada y opt-in.
- Meta cobra por conversación y categoría; el país influye en la tarifa.
- Flows y catálogo/carrito convierten el WhatsApp en un canal de ventas completo.
