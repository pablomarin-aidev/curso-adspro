# Clase 6 — WhatsApp + Meta Ads + Conversion API (CAPI)

**Módulo 6 · MEDICIÓN & PAUTA · ~8 min**
**Formato:** puros bullets, contenido completo de la clase (alternativa a `guiones/`).

- El filtro real de clientes no pasa en el chat, pasa en la pauta.
- El algoritmo de Meta decide a quién mostrarle el anuncio; para decidir bien necesita saber quién de los que llegaron realmente compró.
- Conectar la venta del chat con el anuncio que la trajo hace que la pauta deje de traer curiosos y empiece a traer compradores.

## Lo que aprenderás
- Por qué "mandar gente a WhatsApp" no es una estrategia — recibir chats no es medir ventas.
- Cómo funciona la Conversion API (CAPI) y por qué le gana al pixel solo.
- Cómo amarrar anuncio → chat → venta con CTWA, deduplicación y EMQ.

## Por qué "mandar gente a WhatsApp" no es una estrategia
- Error común: poner un anuncio, dirigirlo a WhatsApp y dar por hecho que el trabajo terminó.
- Si vendes, asumes que el anuncio funcionó; si no, asumes que estaba malo — en ambos casos se está adivinando.
- El problema es de información: Meta trae conversaciones, pero no sabe cuáles terminaron en venta.
- Optimizar por "mensajes iniciados" = optimizar por curiosos. Optimizar por "compras" = optimizar por clientes.

## CAPI: medir desde el servidor, no solo desde el navegador
- El **pixel** reporta desde el navegador del usuario. Tres debilidades: bloqueadores de anuncios lo desactivan, navegadores restringen el rastreo, en móvil la señal se pierde fácil.
- La **Conversion API (CAPI)** mide desde el **servidor**: el sistema envía el evento a Meta de servidor a servidor, sin depender del navegador.
- Analogía: pixel = mensajero cruzando la ciudad con tráfico; CAPI = canal directo que no se pierde en el camino.
- La venta por WhatsApp se cierra en el chat, del lado del servidor — por eso CAPI no es opcional, es la forma correcta de medir.

## CTWA y el referral payload: de qué anuncio vino cada chat
- **CTWA (Click-to-WhatsApp):** anuncios que abren directamente la conversación de WhatsApp, en vez de llevar a una web.
- Su valor real: el **referral payload** — una "etiqueta invisible" en el primer mensaje que indica de qué campaña, conjunto de anuncios y anuncio específico vino el chat.
- Con ese dato se amarra la cadena completa: **anuncio → chat → conversación → venta**.
- Al reportarle a Meta que la venta salió de ese anuncio concreto, el algoritmo empieza a volverse preciso.

## Eventos y deduplicación: no contar lo mismo dos veces
- Un **evento** es cada acción reportada a Meta: chat iniciado, lead generado, compra (con valor y moneda).
- Riesgo si se usan pixel y CAPI a la vez: la misma compra se cuenta dos veces, inflando resultados.
- La **deduplicación** lo evita con un identificador único (*event ID*) por evento; si el mismo ID llega por los dos canales, se cuenta una sola vez.
- Regla: un evento, un ID.

## EMQ: que Meta entienda bien las conversiones
- **EMQ (Event Match Quality):** calidad de coincidencia — qué tan bien Meta emparejó el evento con una persona real de su plataforma.
- Importa porque si Meta no identifica quién compró, esa compra le sirve poco para aprender.
- Lo que sube la EMQ: enviar parámetros de la persona junto al evento, de forma segura y hasheada — teléfono, correo, nombre, ciudad.
- Ventaja en WhatsApp: ya se tiene el teléfono verificado del cliente, una de las señales que más eleva la EMQ.

## Cómo todo esto sube el ROAS
- Juntando las piezas (CAPI desde el servidor + referral payload amarrando chat con anuncio + deduplicación sin ruido + EMQ con buena calidad), Meta recibe datos limpios de quién compró de verdad.
- Con eso, el algoritmo sale más rápido de la fase de aprendizaje y busca gente parecida a los compradores, no a los curiosos.
- El chat no filtra clientes, el chat cierra ventas; quien filtra es el algoritmo, si se le entregan los datos.

## Recurso: configurar y verificar un evento CAPI en Events Manager
- Entrar a Events Manager en el Administrador de anuncios y seleccionar el origen de datos correcto.
- Identificar o crear el evento de conversión (ej. Compra / *Purchase*), definiendo valor y moneda.
- Configurar el envío por CAPI, asegurando que se dispare desde el servidor, no solo desde el navegador.
- Incluir los parámetros de coincidencia de forma segura y hasheada — especialmente el teléfono del cliente de WhatsApp.
- Asignar un event ID único para habilitar deduplicación si también se usa pixel.
- Enviar un evento de prueba con el probador de eventos (*Test Events*) y verificar que caiga en tiempo real.
- Revisar la Event Match Quality del evento y comprobar cómo sube al incluir el teléfono del cliente.

## Para recordar
- El filtro real no ocurre en el chat, ocurre en la pauta — Meta filtra si se le dan buenos datos.
- CAPI mide desde el servidor y le gana al pixel solo, sobre todo cuando la venta se cierra en WhatsApp.
- El referral payload de CTWA dice de qué anuncio vino cada chat: amarra anuncio → chat → venta.
- La deduplicación (un evento, un ID) evita contar la misma compra dos veces.
- La EMQ mide qué tan bien Meta empareja el evento con una persona real; el teléfono verificado es una de las mejores señales.
- Con buen tracking, el algoritmo aprende más rápido y busca compradores — y ahí mejora el ROAS.
