# Clase 11 — Casos de uso reales

**Módulo 11 · CASOS REALES · ~7 min**
**Formato:** puros bullets cortos, contenido completo de la clase (alternativa a `guiones/`).

- Hasta acá, teoría: la API, los templates, los flujos.
- Ahora, siete sectores reales.
- La mecánica es siempre la misma.
- Lo único que cambia es dónde se aprieta el botón.

## Lo que aprenderás
- Cómo la API resuelve un problema en siete sectores.
- Qué medir antes y después de automatizar.
- Cómo se ve un caso real de punta a punta, con MergeOn de ejemplo.

## E-commerce: el catálogo que vende solo
- Problema: preguntan "¿tienes esta talla?" a las 11pm y nadie responde.
- Venta perdida.
- Mecánica: la API conecta el catálogo directo a WhatsApp.
- El cliente ve producto, precio y foto sin salir del chat.
- Se automatiza: bienvenida, muestra de productos, armado del pedido.
- Resultado: la vitrina vende incluso sin nadie atendiendo.

## Restaurantes: pedidos sin saturar el teléfono
- Problema: en hora pico el teléfono colapsa.
- Se pierden pedidos y direcciones mal anotadas.
- Mecánica: menú por WhatsApp con botones.
- El cliente arma pedido y confirma dirección.
- Se automatiza: confirmación, tiempo estimado, aviso de envío.
- Resultado: un flujo que no se equivoca con la dirección.

## Servicios: agendar sin ping-pong
- Problema: diez mensajes para cuadrar una sola cita.
- Mecánica: el cliente ve horarios y elige uno.
- La cita queda agendada sin intervención manual.
- Se automatiza: recordatorio el día anterior.
- Resultado: se deja de operar como secretaria.

## Leads de alto ticket: filtrar antes de invertir tiempo
- Problema: la pauta trae 100 mensajes, solo 10 califican.
- Se responden los 100 a mano.
- Mecánica: la automatización pregunta primero presupuesto y urgencia.
- Solo los que califican llegan a un humano.
- Resultado: el mejor vendedor habla con quien sí compra.

## Recuperación de carritos
- Problema: el cliente empezó a comprar y desapareció.
- Mecánica: el sistema detecta el carrito abandonado.
- Dispara un mensaje por evento, no manual.
- Se automatiza: recordatorio con el producto dejado, y un incentivo si aplica.

## Seguimiento comercial
- Problema: "te escribo el lunes" y se olvida.
- El lead se enfría.
- Mecánica: secuencia programada — día 1, día 3, día 7.
- Si el cliente responde, entra un humano.
- Resultado: el seguimiento no depende de la memoria de nadie.

## Reactivación: despertar la base dormida
- Problema: cientos de clientes que compraron una vez y no volvieron.
- Mecánica: campaña por template a la base inactiva.
- Se segmenta por quién compró qué.
- Resultado: la base vieja no está muerta, está dormida.

## Los números que importan
- Medir antes y después:
  - Tiempo de respuesta.
  - Tasa de respuesta.
  - Carritos recuperados.
- El número que importa es el del propio negocio, no el de un caso ajeno.

## Recurso: un caso real de punta a punta (stack MergeOn)
- **Situación:** leads por pauta que se enfriaban por falta de seguimiento.
- **Qué se automatizó:**
  - Captura del lead vía webhook.
  - Calificación inicial automática.
  - Secuencia de seguimiento para los que no responden.
  - Paso a un humano cuando el lead responde.
- **Resultado:** antes → después *(cifra según el caso real)*.
- Nada nuevo: se conectaron piezas ya conocidas en un solo flujo.

## Para recordar
- La misma tecnología resuelve problemas de sectores distintos.
- Cada caso se sostiene en piezas ya conocidas.
- La diferencia: uno mide su antes y después, el otro adivina.
- Escoger el caso que más se parezca al propio negocio.
