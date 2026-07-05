# Guion — Clase 5: La API por dentro (sin tecnicismos)

> Curso: AdsPRO · Módulo 5 · LA API POR DENTRO · ~12 min
> Formato: contenido a grabar (puntos a decir, no palabra por palabra).
> Voz: español colombiano, "tú", clara y didáctica.
> Objetivo: explicar la API en lenguaje simple y por qué no basta con la app de WhatsApp.

---

## 1. Hook
- Arranca directo: "Si estás usando la app de WhatsApp para vender, estás manejando un carro con freno de mano puesto."
- Suelta la promesa: "En los próximos 12 minutos vas a entender qué es la API de WhatsApp por dentro, sin tecnicismos, y por qué es lo que separa a un negocio que responde manual de uno que vende en automático 24/7."
- Aterriza el dolor real: la app te obliga a estar tú, con el celular en la mano, respondiendo uno por uno. No conecta con tu CRM, no lanza campañas, no atiende mientras duermes. La API sí.
- Deja claro qué NO es esto: "No te voy a llenar de código. Te voy a enseñar a pensar como dueño de negocio que entiende su herramienta."

## 2. Desarrollo (lo que cubres)

### Qué es una API (la analogía del mesero)
- Explica sin miedo: API significa "interfaz de programación", pero olvídate del nombre. Piénsalo como un mesero.
- Tú (o tu CRM, tu página, tu bot) le pides algo al mesero: "manda este mensaje a este número". El mesero lo lleva a la cocina de WhatsApp y te trae la respuesta.
- La app de WhatsApp es como cocinar tú mismo: solo puedes hacer un plato a la vez. La API es tener meseros que atienden cientos de mesas al tiempo, sin que tú toques nada.
- Punto clave para grabar: la API no reemplaza WhatsApp, es la puerta oficial de Meta para que OTROS programas hablen con WhatsApp por ti.

### Qué te permite hacer la API
- Mensajes automatizados: confirmaciones de pedido, recordatorios, seguimientos que salen solos.
- Notificaciones: "tu pedido va en camino", "tu cita es mañana", disparadas por un evento sin que tú escribas nada.
- Bots y agentes de IA: responden preguntas, califican clientes y agendan mientras tú haces otra cosa.
- Integración con todo tu ecosistema: CRM, tu página web, formularios y hasta tus anuncios de Meta. El cliente da clic en el anuncio y ya está hablándote por WhatsApp.
- Escalabilidad: pasar de atender 20 chats a 2.000 sin contratar 20 personas. Ese es el salto.

### Cómo se ve por dentro (arquitectura simple)
- Dibuja el camino en 4 piezas, de izquierda a derecha:
- Uno: tu **número** de WhatsApp Business (el que verá el cliente).
- Dos: el **BSP** (Business Solution Provider), el proveedor oficial aprobado por Meta que te da acceso a la API. Es tu conexión legal y técnica.
- Tres: tu **CRM o plataforma**, donde vive la conversación, el contacto y la automatización.
- Cuatro: tus canales de entrada — **web, formularios y anuncios** que empujan gente hacia ese número.
- Frase para grabar: "El número es la cara, el BSP es el puente, el CRM es el cerebro."

### Webhooks: cómo entra y sale un mensaje
- Define simple: un webhook es un "aviso automático". Cada vez que pasa algo en WhatsApp, Meta le toca la puerta a tu sistema y le dice qué pasó.
- Cuando ENTRA un mensaje: el cliente escribe → Meta lo detecta → dispara el webhook → tu plataforma recibe el mensaje al instante y decide qué hacer (responder, avisar a un asesor, activar el bot).
- Cuando SALE un mensaje: tu plataforma le pide a la API que envíe → la API lo entrega al cliente → y te devuelve otro aviso: "entregado", "leído", "falló".
- Insiste: sin webhooks no hay tiempo real. Con ellos, tu negocio "escucha" WhatsApp 24/7.

### La ventana de 24 horas y las plantillas (HSM)
- Regla de oro de Meta: cuando un cliente te escribe, se abre una **ventana de 24 horas** en la que puedes responderle libremente, con el texto que quieras.
- Pasadas esas 24 horas de silencio, ya NO puedes escribirle lo que se te dé la gana. Solo puedes mandarle una **plantilla** aprobada por Meta (HSM).
- Y antes de todo eso está el **opt-in**: el permiso. El cliente tiene que haber aceptado que le escribas. Sin permiso, Meta te frena. Esto no es capricho, es lo que mantiene tu número sano y sin bloqueos.
- Frase para grabar: "Dentro de las 24 horas eres libre; fuera de ellas, necesitas plantilla y permiso."

### Plantillas / HSM por dentro
- Qué son: mensajes prediseñados que Meta revisa y aprueba antes de que los puedas usar para iniciar conversación.
- Categorías (nómbralas claras):
- **Marketing** — promociones, novedades, reactivaciones.
- **Utility** (utilidad) — confirmaciones, actualizaciones de pedido, recordatorios de cita.
- **Authentication** (autenticación) — códigos de verificación, OTP.
- Qué llevan por dentro: **variables** (los espacios que se rellenan con el nombre, el número de pedido, la fecha), **botones** (llamada a la acción, respuesta rápida) y hasta **carruseles** para mostrar varios productos.
- Por qué te las rechazan (esto vale oro para el alumno): texto que parece spam, promesas exageradas, variables mal armadas o vacías, categoría equivocada (mandar marketing disfrazado de utility), links sospechosos o faltas de contexto. Menciona que rechazan y toca corregir y reenviar.

### Cuánto te cobra Meta (modelo de precios)
- Explica el concepto sin inventar números: Meta ya no cobra por cada mensajito suelto, cobra por **conversación** dentro de una ventana, y el precio cambia según la **categoría** (marketing suele ser más caro que utility o servicio).
- El país también pesa: la tarifa por conversación varía según el mercado.
- Ahí van los rangos: (valores a insertar según la fuente del curso).
- Idea que se lleva el alumno: no es "gratis mandar WhatsApp", pero bien usado el costo por venta es ridículamente bajo comparado con otros canales.

### Capacidades avanzadas (lo que casi nadie usa todavía)
- **WhatsApp Flows**: formularios nativos DENTRO del chat. El cliente llena datos, agenda, cotiza o elige opciones sin salir de WhatsApp ni ir a una página externa. Menos fricción, más conversión.
- **Catálogo y carrito**: puedes mostrar tus productos, que el cliente los agregue a un carrito y arme el pedido sin abandonar la conversación. Es como tener una tiendita dentro del chat.
- Cierra el bloque: "Estas dos cosas convierten tu WhatsApp de un canal de mensajes a un canal de ventas completo."

## 3. Demo / Práctica
- Anuncia el 🛠️: "Vamos a ver esto en vivo, no en teoría."
- Recorre el setup real paso a paso en pantalla: entrar a **Business Manager**, hacer la **verificación** del negocio, dar de alta el **número**, y configurar el **display name** (el nombre que verá el cliente).
- Muestra el momento clave: envía un mensaje de prueba desde un celular al número conectado y señala cómo **entra por el webhook** en la plataforma real, en vivo, sin recargar nada.
- Recalca lo que están viendo: "Eso que acaba de aparecer solo es el webhook haciendo su trabajo. Así 'escucha' tu negocio."

## 4. Cierre + puente al siguiente módulo
- Resume en una frase: "La app de WhatsApp te deja hablar; la API te deja construir un negocio que vende solo."
- Refuerza los 4 conceptos que no pueden olvidar: ventana de 24 horas, plantillas y permiso, webhooks y el modelo de precio por conversación.
- Puente: "Ya sabes qué es la API por dentro y de qué es capaz. En el siguiente módulo bajamos a la práctica pura: vamos a dejar tu número conectado y funcionando, con todo listo para recibir tu primer cliente en automático. Nos vemos ahí."
