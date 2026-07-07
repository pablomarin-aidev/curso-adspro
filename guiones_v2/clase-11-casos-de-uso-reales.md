# Clase 11 — Casos de uso reales

**Módulo 11 · CASOS REALES · ~7 min**
**Formato:** puros bullets, contenido completo de la clase (alternativa a `guiones/`).

- Hasta acá, teoría: la API, los templates, los flujos.
- Ahora, siete sectores reales donde la mecánica es siempre la misma — lo único que cambia es dónde se aprieta el botón.

## Lo que aprenderás
- Cómo la API y la automatización resuelven un problema concreto en siete sectores (e-commerce, restaurantes, servicios, alto ticket, carritos, seguimiento y reactivación).
- Qué medir antes y después para saber si la automatización realmente movió la aguja.
- Cómo se ve un caso real de punta a punta: situación, qué se automatizó y resultado, con MergeOn de ejemplo.

## E-commerce: el catálogo que vende solo
- Problema: cliente pregunta "¿tienes esta talla?" a las 11pm y no recibe respuesta hasta el día siguiente — venta perdida.
- Mecánica: la API conecta el catálogo directo a WhatsApp; el cliente ve producto, precio y foto sin salir del chat.
- Se automatiza: bienvenida, muestra de productos, armado del pedido cuando el cliente elige.
- Resultado: la vitrina no cierra, vende incluso sin nadie atendiendo.

## Restaurantes: pedidos sin saturar el teléfono
- Problema: en hora pico el teléfono colapsa, se pierden pedidos, direcciones mal anotadas.
- Mecánica: menú por WhatsApp con botones — el cliente arma pedido, confirma dirección, pasa directo a cocina.
- Se automatiza: confirmación del pedido, tiempo estimado, aviso cuando sale el domiciliario.
- Resultado: un flujo que no se equivoca con la dirección ni olvida el ají.

## Servicios: agendar sin ping-pong
- Problema: "¿tienes cupo el martes?" seguido de diez mensajes para cuadrar una cita.
- Mecánica: el cliente ve horarios disponibles, elige uno, la cita queda agendada y confirmada sin intervención manual.
- Se automatiza: recordatorio el día anterior — reduce citas perdidas y huecos en la agenda.
- Resultado: se deja de operar como secretaria y se vuelve al negocio.

## Leads de alto ticket: filtrar antes de invertir tiempo
- Problema: la pauta trae 100 mensajes, solo 10 califican de verdad, pero se responden los 100 a mano.
- Mecánica: la automatización hace primero las preguntas de calificación (presupuesto, urgencia, encaje).
- Solo los que califican llegan a un humano; los demás reciben información y quedan en base para nutrir después.
- Resultado: el mejor vendedor habla con quien sí compra, no con quien solo pregunta.

## Recuperación de carritos: rescatar la venta a medias
- Problema: el cliente estaba interesado, empezó a comprar y desapareció — plata a un clic de cerrarse.
- Mecánica: el sistema detecta el carrito abandonado y dispara un mensaje por evento, no manual.
- Se automatiza: recordatorio con el producto dejado y, cuando aplica, un incentivo — a la hora exacta.

## Seguimiento comercial: que ningún lead se enfríe
- Problema: el vendedor promete "te escribo el lunes" y se le olvida — el lead se enfría.
- Mecánica: secuencia de seguimiento programada — día 1, día 3, día 7 — con mensajes que llegan solos.
- Si el cliente responde, entra un humano; si no, la secuencia sigue nutriéndolo.
- Resultado: el seguimiento deja de depender de la memoria de nadie.

## Reactivación: despertar la base dormida
- Problema: cientos de clientes que compraron una vez y no volvieron — plata quieta.
- Mecánica: campaña por template dirigida a la base inactiva — novedad, oferta o recordatorio.
- Se segmenta por quién compró qué, para que cada persona reciba el mensaje relevante.
- Resultado: la base vieja no está muerta, está dormida.

## Los números que importan: mide el antes y el después
- Indicadores a medir en cada caso:
  - Tiempo de respuesta: antes → después *(cifra según el caso real)*.
  - Tasa de respuesta: antes → después *(cifra según el caso real)*.
  - Carritos recuperados: antes → después *(cifra según el caso real)*.
- El número que importa es el del propio negocio medido antes y después, no el de un caso ajeno.

## Recurso: un caso real de punta a punta (stack MergeOn)
- **Situación:** un negocio recibía leads por pauta, pero se enfriaban por falta de seguimiento constante; los mensajes se atendían de a poco, sin proceso que asegurara que ninguno se cayera.
- **Qué se automatizó:**
  - Captura del lead entrante vía webhook, registrando al contacto apenas escribe.
  - Calificación inicial automática con las preguntas clave antes de involucrar a una persona.
  - Secuencia de seguimiento programada para los que no responden de inmediato.
  - Paso a un humano cuando el lead responde, para cerrar con contexto.
- **Resultado:** antes → después *(cifra a insertar según el caso real)*.
- Nada nuevo inventado: se conectaron las piezas ya conocidas — webhook, calificación, secuencia y traspaso a humano — en un solo flujo.

## Para recordar
- La misma tecnología resuelve problemas de sectores muy distintos; solo cambia dónde se aplica.
- Cada caso se sostiene en piezas ya conocidas: catálogo, templates, flujos, webhooks y secuencias de seguimiento.
- La diferencia entre quien aprovecha la automatización y quien no: uno mide su antes y después, el otro adivina.
- Escoger el caso que más se parezca al propio negocio: ese es el punto de partida para montarlo.
