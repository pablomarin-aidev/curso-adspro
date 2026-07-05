# Clase 5 — La API por dentro (sin tecnicismos)

**Módulo 5 · LA API POR DENTRO · ~12 min**

### Por qué la app de WhatsApp se te queda corta para vender

La aplicación normal de WhatsApp te obliga a estar tú, con el celular en la mano, respondiendo uno por uno. No conecta con tu CRM, no lanza campañas y no atiende mientras duermes. La API de WhatsApp es la puerta oficial de Meta para que otros programas hablen con WhatsApp por ti. En esta clase la entiendes por dentro, sin código y sin tecnicismos.

## Lo que aprenderás
1. Qué es una API y qué te permite hacer que la app normal no puede.
2. Cómo viaja un mensaje por dentro: número, BSP, CRM, webhooks y la ventana de 24 horas.
3. Cómo funcionan las plantillas (HSM), cuánto te cobra Meta y qué capacidades avanzadas existen.

## Qué es una API (y qué te permite hacer)

API significa "interfaz de programación", pero olvídate del nombre. Piénsalo como un mesero: tú, tu CRM o tu bot le piden algo ("manda este mensaje a este número"), el mesero lo lleva a la cocina de WhatsApp y te trae la respuesta. La app normal es cocinar tú mismo un plato a la vez; la API es tener meseros que atienden cientos de mesas al tiempo.

La API no reemplaza WhatsApp: es la conexión oficial que permite que otros sistemas trabajen con él. Con ella puedes:

- **Mensajes automatizados** — confirmaciones, recordatorios y seguimientos que salen solos.
- **Notificaciones** — "tu pedido va en camino", "tu cita es mañana", disparadas por un evento.
- **Bots y agentes de IA** — responden, califican clientes y agendan sin que estés presente.
- **Integración con tu ecosistema** — CRM, página web, formularios y anuncios de Meta (el cliente da clic en el anuncio y ya te está escribiendo).
- **Escalabilidad** — pasar de 20 chats a 2.000 sin contratar 20 personas.

## Arquitectura simple: cómo se conecta todo

El camino de tu operación tiene cuatro piezas, de izquierda a derecha:

| Pieza | Qué es | Rol |
|---|---|---|
| **Número** | Tu línea de WhatsApp Business | La cara que ve el cliente |
| **BSP** | Business Solution Provider (proveedor oficial aprobado por Meta) | El puente legal y técnico hacia la API |
| **CRM / plataforma** | Donde vive la conversación, el contacto y la automatización | El cerebro |
| **Web, formularios y anuncios** | Canales de entrada | Empujan gente hacia el número |

En una frase: el número es la cara, el BSP es el puente, el CRM es el cerebro.

## Webhooks: cómo entra y sale un mensaje

Un webhook es un "aviso automático". Cada vez que pasa algo en WhatsApp, Meta le toca la puerta a tu sistema y le dice qué pasó.

- **Cuando entra un mensaje:** el cliente escribe → Meta lo detecta → dispara el webhook → tu plataforma recibe el mensaje al instante y decide qué hacer (responder, avisar a un asesor, activar el bot).
- **Cuando sale un mensaje:** tu plataforma le pide a la API que envíe → la API lo entrega → y devuelve otro aviso de estado: entregado, leído o falló.

Sin webhooks no hay tiempo real. Con ellos, tu negocio "escucha" WhatsApp las 24 horas.

## La ventana de 24 horas, las plantillas y el permiso

Meta tiene una regla de oro que debes tener grabada:

- **Ventana de 24 horas:** cuando un cliente te escribe, se abre una ventana de 24 horas en la que puedes responderle libremente, con el texto que quieras.
- **Fuera de la ventana:** pasadas esas 24 horas de silencio, ya no puedes escribirle texto libre. Solo puedes iniciar con una **plantilla (HSM)** aprobada por Meta.
- **Opt-in (permiso):** antes de todo, el cliente tuvo que aceptar que le escribas. Sin permiso, Meta te frena. Esto mantiene tu número sano y sin bloqueos.

Dentro de las 24 horas eres libre; fuera de ellas, necesitas plantilla y permiso.

## Plantillas / HSM por dentro

Las plantillas son mensajes prediseñados que Meta revisa y aprueba antes de que puedas usarlos para iniciar una conversación.

**Categorías:**

| Categoría | Para qué sirve | Ejemplos |
|---|---|---|
| **Marketing** | Promoción y reactivación | Ofertas, novedades, "vuelve con nosotros" |
| **Utility** (utilidad) | Transacciones y servicio | Confirmación de pedido, recordatorio de cita |
| **Authentication** (autenticación) | Seguridad | Códigos de verificación, OTP |

**Qué llevan por dentro:**

- **Variables** — espacios que se rellenan con el nombre, el número de pedido o la fecha.
- **Botones** — llamada a la acción o respuestas rápidas.
- **Carruseles** — para mostrar varios productos en un solo mensaje.

**Por qué te las rechazan:**

- Texto que parece spam o con promesas exageradas.
- Variables mal armadas o vacías.
- Categoría equivocada (marketing disfrazado de utility).
- Links sospechosos o mensajes sin contexto.

Cuando rechazan una plantilla, toca corregirla y reenviarla a revisión.

## Cuánto te cobra Meta

Meta ya no cobra por cada mensaje suelto: cobra por **conversación** dentro de una ventana, y el precio cambia según la **categoría** (marketing suele costar más que utility o servicio). El **país** también influye, porque la tarifa por conversación varía según el mercado.

- Rangos y tarifas: (valores a insertar según la fuente del curso).

La idea que te llevas: no es "gratis mandar WhatsApp", pero bien usado el costo por venta es muy bajo frente a otros canales.

## Capacidades avanzadas

- **WhatsApp Flows** — formularios nativos dentro del chat. El cliente agenda, cotiza o elige opciones sin salir de WhatsApp ni ir a una página externa. Menos fricción, más conversión.
- **Catálogo y carrito** — muestras tus productos, el cliente los agrega a un carrito y arma el pedido sin abandonar la conversación. Es una tiendita dentro del chat.

Estas dos capacidades convierten tu WhatsApp de un canal de mensajes a un canal de ventas completo.

## Recurso: pasos del setup real (en orden)

Para dejar tu número operando con la API, este es el orden del montaje:

1. **Business Manager** — entra y configura tu Business Manager de Meta.
2. **Verificación** — completa la verificación del negocio.
3. **Número** — da de alta el número que usará la API.
4. **Display name** — configura el nombre que verá el cliente.

Con esto listo, tu número queda conectado y empieza a recibir mensajes que entran por el webhook a tu plataforma.

## Para recordar
- La app te deja hablar; la API te deja construir un negocio que vende solo.
- El camino del mensaje: número → BSP → CRM → web/formularios/anuncios, con webhooks avisando en tiempo real.
- Dentro de las 24 horas respondes libre; fuera de ellas necesitas plantilla (HSM) aprobada y opt-in.
- Meta cobra por conversación y por categoría; el país influye en la tarifa.
- Flows y catálogo/carrito convierten tu WhatsApp en un canal de ventas completo.
