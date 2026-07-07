# Clase 6 — WhatsApp + Meta Ads + Conversion API (CAPI)

**Módulo 6 · MEDICIÓN & PAUTA · ~8 min**

### El filtro de tus clientes no pasa en el chat, pasa en la pauta

La mayoría cree que a los curiosos los filtra en la conversación de WhatsApp. La verdad es que el filtro real ocurre mucho antes: en el algoritmo de Meta, que decide a quién le muestra tu anuncio. Para que decida bien, necesita saber quién de los que llegaron realmente te compró. En esta clase conectas la venta que cierras en el chat con el anuncio que la trajo — y así tu pauta deja de traerte curiosos y empieza a traerte compradores.

## Lo que aprenderás
1. **Por qué "mandar gente a WhatsApp" no es una estrategia.** Recibir chats no es lo mismo que medir ventas; sin datos, Meta optimiza a ciegas.
2. **Cómo funciona la Conversion API (CAPI) y por qué le gana al pixel solo.** Medir desde el servidor no depende del navegador y no pierde eventos.
3. **Cómo amarrar anuncio → chat → venta con CTWA, deduplicación y EMQ.** Para que Meta entienda quién compró de verdad y suba tu ROAS.

## Por qué "mandar gente a WhatsApp" no es una estrategia

El error más común es poner un anuncio, dirigirlo a WhatsApp y dar por hecho que el trabajo terminó. Llegan chats, los contestas, y si vendes asumes que el anuncio funcionó; si no vendes, asumes que estaba malo. En ambos casos estás adivinando.

El problema es de información. Meta te trae conversaciones, pero por sí sola no sabe cuáles terminaron en una venta. Y si no sabe quién compró, no puede aprender a buscarte más personas parecidas a ese comprador. Optimizar por "mensajes iniciados" es optimizar por curiosos; optimizar por "compras" es optimizar por clientes. Esa diferencia es la que separa una cuenta que quema plata de una rentable.

## CAPI: medir desde el servidor, no solo desde el navegador

Durante años todo se midió con el **pixel**: un fragmento de código en tu página que le reporta a Meta lo que ocurre en el navegador del usuario. Hoy el pixel tiene tres debilidades grandes: los bloqueadores de anuncios lo desactivan, los navegadores están restringiendo el rastreo, y en móvil la señal se pierde con facilidad. El resultado es que pierdes eventos, y los que llegan, llegan incompletos.

La **Conversion API (CAPI)** resuelve esto midiendo desde el **servidor**: tu sistema le envía el evento a Meta de servidor a servidor, sin depender del navegador del usuario. Si el pixel es confiar en un mensajero que cruza la ciudad con tráfico, CAPI es mandar la información por un canal directo que no se pierde en el camino.

Para vender por WhatsApp, esto es determinante: la venta no se cierra en un navegador con pixel, se cierra en el chat, del lado del servidor. Por eso CAPI no es un extra opcional — es la forma correcta de medir conversiones que nacen en WhatsApp.

## CTWA y el referral payload: de qué anuncio vino cada chat

**CTWA (Click-to-WhatsApp)** son anuncios que, en lugar de llevar a una página web, abren directamente tu conversación de WhatsApp. Su verdadero valor está en un dato que casi nadie aprovecha: el **referral payload**.

Cuando alguien te escribe desde un anuncio CTWA, su primer mensaje llega acompañado de una "etiqueta invisible" que indica exactamente de qué anuncio provino: el identificador de la campaña, del conjunto de anuncios y del anuncio específico. Es decir, desde el primer segundo sabes que ese chat nació del anuncio X, sin adivinar.

Con ese dato amarras toda la cadena: **anuncio → chat → conversación → venta**. Cuando la persona compra, puedes reportarle a Meta que esa venta salió de ese anuncio concreto, y ahí es donde el algoritmo empieza a volverse preciso.

## Eventos y deduplicación: no contar lo mismo dos veces

Un **evento** es cada acción que le reportas a Meta: se inició un chat, se generó un lead, se hizo una compra — con su valor y su moneda cuando aplica.

Si usas pixel y CAPI al mismo tiempo, aparece un riesgo: que la misma compra se cuente dos veces, una por cada canal. Eso infla tus resultados y confunde al algoritmo. La **deduplicación** lo evita asignándole a cada evento un identificador único (un *event ID*). Si a Meta le llega el mismo ID por los dos canales, entiende que es el mismo evento y lo cuenta una sola vez.

La regla es sencilla: un evento, un ID. Mismo ID enviado por pixel y por CAPI equivale a una sola compra contada. Así los números que ves reflejan la realidad.

## EMQ: que Meta entienda bien tus conversiones

**EMQ (Event Match Quality)** es la calidad de coincidencia del evento: una nota que Meta asigna según qué tan bien pudo emparejar tu evento con una persona real de su plataforma. Importa porque si Meta no logra identificar quién compró, esa compra le sirve de poco para aprender. Un evento con buena coincidencia le confirma que una persona real compró, y con eso sale a buscar más personas parecidas.

Lo que sube la EMQ es enviar buenos parámetros de la persona junto al evento, siempre de forma segura y hasheada: teléfono, correo, nombre, ciudad. Entre más señales limpias envíes, más alta es la nota. En WhatsApp tienes una ventaja enorme: ya cuentas con el teléfono verificado del cliente, uno de los datos que más eleva la EMQ. Es una señal de alta calidad que muchos tienen a la mano y no usan.

## Cómo todo esto sube tu ROAS

Al juntar las piezas — CAPI enviando la señal completa desde el servidor, el referral payload amarrando el chat con el anuncio, la deduplicación evitando el ruido y la EMQ elevando la calidad de la señal — Meta recibe datos limpios de quién compró de verdad. Con esa información, su algoritmo sale más rápido de la fase de aprendizaje y empieza a buscar gente parecida a tus compradores, no a tus curiosos.

Ahí es donde el filtro ocurre en la pauta: Meta deja de gastar presupuesto mostrándole el anuncio a quien nunca iba a comprar. El chat no filtra clientes, el chat cierra ventas; quien filtra es el algoritmo, pero solo si tú le entregas los datos para hacerlo.

## Recurso: configurar y verificar un evento CAPI en Events Manager

Sigue estos pasos para dejar tu medición funcionando y confirmada:

1. **Entra a Events Manager** en tu Administrador de anuncios de Meta y selecciona el origen de datos correcto (tu cuenta / dataset de conversiones).
2. **Identifica o crea el evento de conversión** que quieres medir, por ejemplo una Compra (*Purchase*), definiendo su valor y su moneda.
3. **Configura el envío por CAPI**, asegurándote de que el evento se dispare desde el servidor y no solo desde el navegador.
4. **Incluye los parámetros de coincidencia** de forma segura y hasheada — especialmente el teléfono del cliente de WhatsApp — para maximizar la EMQ.
5. **Asigna un event ID único** al evento para habilitar la deduplicación si también usas pixel.
6. **Envía un evento de prueba** con el probador de eventos (*Test Events*) y verifica que caiga en tiempo real; así confirmas que la tubería servidor a servidor funciona antes de invertir en pauta.
7. **Revisa la Event Match Quality** del evento en Events Manager y observa qué parámetros la mejoran; comprueba cómo sube la nota al incluir el teléfono del cliente.

## Para recordar
- El filtro real de tus clientes no ocurre en el chat, ocurre en la pauta: Meta filtra por ti si le das buenos datos.
- CAPI mide desde el servidor y por eso le gana al pixel solo, sobre todo cuando la venta se cierra en WhatsApp.
- El referral payload de CTWA te dice de qué anuncio vino cada chat: amarra anuncio → chat → venta.
- La deduplicación (un evento, un ID) evita contar la misma compra dos veces.
- La EMQ mide qué tan bien Meta empareja tu evento con una persona real; el teléfono verificado de WhatsApp es una de tus mejores señales.
- Con buen tracking, el algoritmo aprende más rápido y busca compradores, no curiosos — y ahí es donde mejora tu ROAS.
