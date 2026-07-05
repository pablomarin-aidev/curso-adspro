# Guion — Clase 6: WhatsApp + Meta Ads + Conversion API (CAPI) ⭐

> Curso: AdsPRO · Módulo 6 · MEDICIÓN & PAUTA · ~11 min
> Formato: contenido a grabar (puntos a decir, no palabra por palabra).
> Voz: español colombiano, "tú", clara y con energía.
> Objetivo: conectar ventas con pauta. Aquí se filtran los curiosos — no en el chat, como se suele creer.

---

## 1. Hook
- Arranca directo: "Si tú crees que el filtro de tus clientes pasa en el chat de WhatsApp… déjame decirte que estás mirando el lugar equivocado."
- El filtro real pasa mucho antes, en la pauta. Es Meta la que decide a quién le muestra tu anuncio. Y para que decida bien, necesita saber quién de los que llegaron TE COMPRÓ.
- Suelta la promesa: "En esta clase te voy a mostrar cómo conectar la venta que cierras en WhatsApp con el anuncio que la trajo. Cuando aprendas esto, tu pauta deja de traerte curiosos y empieza a traerte compradores. Esa es la clase estrella del curso, así que ponte cómodo."

## 2. Desarrollo (lo que cubres)

### Por qué "mandar gente a WhatsApp" no es una estrategia
- El error más común: la gente pone un anuncio, lo manda a WhatsApp y cree que ya. Reciben chats, contestan, y si venden creen que fue el anuncio; si no venden, creen que el anuncio está malo.
- El problema es que están adivinando. Meta te trae conversaciones, pero no sabe cuáles de esas conversaciones terminaron en plata.
- Y si Meta no sabe quién compró, no puede aprender a buscarte más gente parecida al que compró. Le estás pidiendo que optimice a ciegas.
- Frase para anclar: "Optimizar por 'mensajes iniciados' es optimizar por curiosos. Optimizar por 'compras' es optimizar por clientes. La diferencia entre las dos es la que te separa de un ROAS rentable."

### CAPI: medir desde el servidor, no solo desde el navegador
- Antes todo se medía con el pixel: un pedacito de código en tu página que le avisa a Meta lo que pasa en el navegador del usuario.
- El pixel tiene tres problemas grandes hoy: bloqueadores de anuncios lo apagan, los navegadores están cerrando el rastreo, y en móvil la señal se pierde. Resultado: pierdes eventos, y los que sí llegan, llegan incompletos.
- Aquí entra la Conversion API, o CAPI. Es medir desde el SERVIDOR: tu sistema le manda el evento a Meta de servidor a servidor, sin depender del navegador del usuario.
- Analogía sencilla: el pixel es como confiar en que el mensajero entregue la carta cruzando media ciudad con tráfico. CAPI es mandarla directo por correo interno, sin que el tráfico la pierda.
- Y lo importante para nosotros: WhatsApp no vive en un navegador con pixel. La venta se cierra en el chat, del lado del servidor. Por eso, para vender por WhatsApp, CAPI no es opcional — es LA forma de medir.

### CTWA y el referral payload: saber de qué anuncio vino cada chat
- CTWA significa Click-to-WhatsApp: anuncios que en vez de llevar a una web, abren directo tu chat de WhatsApp.
- La magia está en algo que casi nadie usa: el referral payload. Cuando alguien te escribe desde un anuncio CTWA, el primer mensaje llega con una "etiqueta invisible" que dice de qué anuncio vino — el ID de la campaña, el conjunto y el anuncio.
- Eso quiere decir que, desde el segundo cero, tú sabes: este chat nació del anuncio X. No lo estás adivinando.
- Con eso amarras toda la cadena: anuncio → chat → conversación → venta. Cuando la persona compra, tú le puedes decir a Meta "esta venta salió de ESTE anuncio", y ahí es donde Meta empieza a volverse inteligente.

### Eventos y deduplicación: que no cuentes lo mismo dos veces
- Un "evento" es cada cosa que le reportas a Meta: se inició un chat, hubo un lead, se hizo una compra, con su valor y su moneda.
- Cuando usas pixel Y CAPI al mismo tiempo, corres el riesgo de que la misma compra se cuente dos veces — una por cada canal. Eso te infla los números y confunde al algoritmo.
- La deduplicación resuelve eso: le mandas a cada evento un identificador único (un event ID). Si a Meta le llega el mismo ID por los dos lados, entiende que es el MISMO evento y lo cuenta una sola vez.
- Regla mental: un evento, un ID. Mismo ID por pixel y por CAPI = una sola compra contada. Así los números que ves son reales.

### EMQ: que Meta "entienda" bien tus conversiones
- EMQ es Event Match Quality, o calidad de coincidencia del evento. Es una nota que Meta le pone a qué tan bien pudo emparejar tu evento con una persona real de su plataforma.
- ¿Por qué importa? Porque si Meta no logra saber QUIÉN compró, esa compra le sirve de poco para aprender. Un evento con buena coincidencia le dice a Meta "esta persona real compró", y con eso sale a buscarte más personas parecidas.
- ¿Qué mejora la EMQ? Mandar buenos parámetros de la persona junto al evento — de forma segura y hasheada: teléfono, correo, nombre, ciudad. Entre más señales limpias mandes, más alta la nota.
- En WhatsApp tienes una ventaja enorme: ya tienes el teléfono verificado del cliente. Ese es uno de los datos que más sube la EMQ. Estás sentado sobre oro para el tracking y muchos ni lo usan.

### Cómo todo esto sube tu ROAS
- Junta las piezas: CAPI manda la señal completa desde el servidor, el referral payload amarra el chat con el anuncio, la deduplicación evita el ruido, y la EMQ hace que la señal sea de alta calidad.
- ¿Qué recibe Meta? Datos limpios de quién compró de verdad. Con eso, su algoritmo sale de la fase de aprendizaje más rápido y empieza a buscar gente parecida a tus COMPRADORES, no a tus curiosos.
- Ahí es donde el filtro sucede en la pauta: Meta deja de gastarte plata mostrándole el anuncio a quien nunca iba a comprar.
- Cierre del concepto: "El chat no filtra clientes. El chat cierra ventas. Quien filtra es el algoritmo — pero solo si tú le das los datos para hacerlo. Eso es lo que estás construyendo aquí."

## 3. Demo / Práctica
- Anúnciala: "Vamos a Events Manager y configuramos un evento CAPI de verdad. Sígueme el paso."
- Muestra en pantalla: entrar a Events Manager, ubicar el origen de datos, y crear/identificar el evento de conversión — por ejemplo una Compra (Purchase) con su valor y moneda.
- Manda un evento de PRUEBA: usa el probador de eventos (Test Events) para disparar uno y verlo caer en tiempo real. Explica que estás confirmando que la tubería server-a-server funciona antes de gastar un peso en pauta.
- Lee la calidad: muéstrale dónde aparece la Event Match Quality del evento y qué parámetros la subieron. Señala en vivo cómo mejora la nota cuando incluyes el teléfono del cliente.
- Remata: "¿Viste? En cinco minutos pasaste de adivinar a medir. Y lo que se mide, se puede mejorar."

## 4. Cierre + puente al siguiente módulo
- Recapitula en una frase: "Hoy conectaste la venta de WhatsApp con la pauta: CAPI para medir desde el servidor, CTWA para saber de dónde vino cada chat, deduplicación para no contar de más, y EMQ para que Meta entienda quién compró de verdad."
- Refuerza la idea grande: el filtro de tus clientes no vive en el chat — vive en un algoritmo bien alimentado. Ahora sabes cómo alimentarlo.
- Puente: "Ya sabes MEDIR. En el siguiente módulo bajamos a lo práctico: cómo elegir el proveedor (BSP) correcto para montar todo esto sin que te tumben el número. Nos vemos allá."
