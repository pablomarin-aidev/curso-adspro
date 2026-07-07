# Clase 6 — WhatsApp + Meta Ads + Conversion API (CAPI)

**Módulo 6 · MEDICIÓN & PAUTA · ~8 min**
**Formato:** puros bullets cortos, contenido completo de la clase (alternativa a `guiones/`).

- El filtro real de clientes no pasa en el chat.
- Pasa en la pauta.
- El algoritmo de Meta decide a quién mostrar el anuncio.
- Necesita saber quién de los que llegaron realmente compró.
- Así la pauta deja de traer curiosos y empieza a traer compradores.

## Lo que aprenderás
- Por qué "mandar gente a WhatsApp" no es una estrategia.
- Cómo funciona la Conversion API (CAPI) y por qué le gana al pixel.
- Cómo amarrar anuncio → chat → venta con CTWA, deduplicación y EMQ.

## Por qué "mandar gente a WhatsApp" no es una estrategia
- Error común: poner un anuncio y dar por hecho que el trabajo terminó.
- Si vendes, asumes que el anuncio funcionó.
- Si no, asumes que estaba malo.
- En ambos casos se está adivinando.
- Meta trae conversaciones, pero no sabe cuáles terminaron en venta.
- Optimizar por "mensajes iniciados" = optimizar por curiosos.
- Optimizar por "compras" = optimizar por clientes.

## CAPI: medir desde el servidor
- El **pixel** reporta desde el navegador del usuario.
- Debilidades: bloqueadores lo desactivan, navegadores restringen el rastreo, en móvil se pierde señal.
- La **Conversion API (CAPI)** mide desde el **servidor**.
- Sin depender del navegador.
- Analogía: pixel = mensajero cruzando tráfico; CAPI = canal directo.
- La venta por WhatsApp se cierra en el chat, del lado del servidor.
- Por eso CAPI no es opcional.

## CTWA y el referral payload
- **CTWA:** anuncios que abren directamente la conversación de WhatsApp.
- Su valor real: el **referral payload**.
- Una "etiqueta invisible" en el primer mensaje.
- Indica de qué campaña y anuncio vino el chat.
- Con eso se amarra: anuncio → chat → conversación → venta.
- El algoritmo empieza a volverse preciso.

## Eventos y deduplicación
- Un **evento** es cada acción reportada a Meta: chat, lead, compra.
- Riesgo si se usan pixel y CAPI a la vez: la misma compra se cuenta dos veces.
- La **deduplicación** usa un *event ID* único por evento.
- Si el mismo ID llega por los dos canales, se cuenta una sola vez.
- Regla: un evento, un ID.

## EMQ: que Meta entienda las conversiones
- **EMQ:** calidad de coincidencia del evento con una persona real.
- Si Meta no identifica quién compró, esa compra le sirve poco.
- Sube la EMQ enviar parámetros de la persona, hasheados.
- Teléfono, correo, nombre, ciudad.
- Ventaja en WhatsApp: ya se tiene el teléfono verificado.
- Es una de las señales que más eleva la EMQ.

## Cómo esto sube el ROAS
- CAPI + referral payload + deduplicación + EMQ = datos limpios.
- Meta recibe quién compró de verdad.
- El algoritmo aprende más rápido.
- Busca gente parecida a los compradores, no a los curiosos.
- El chat no filtra clientes, el chat cierra ventas.
- Quien filtra es el algoritmo, si se le entregan los datos.

## Recurso: configurar y verificar un evento CAPI
- Entrar a Events Manager y seleccionar el origen de datos.
- Crear el evento de conversión (ej. Compra), con valor y moneda.
- Configurar el envío desde el servidor.
- Incluir parámetros de coincidencia, especialmente el teléfono.
- Asignar un event ID único para la deduplicación.
- Enviar un evento de prueba y verificar que caiga en tiempo real.
- Revisar la Event Match Quality del evento.

## Para recordar
- El filtro real ocurre en la pauta, no en el chat.
- CAPI mide desde el servidor y le gana al pixel solo.
- El referral payload de CTWA amarra anuncio → chat → venta.
- La deduplicación evita contar la misma compra dos veces.
- La EMQ mide la calidad de coincidencia; el teléfono verificado es clave.
- Con buen tracking, el algoritmo busca compradores y mejora el ROAS.
