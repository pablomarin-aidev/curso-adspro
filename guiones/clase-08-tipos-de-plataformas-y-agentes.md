# Guion — Clase 8: Tipos de plataformas (y los agentes de IA por dentro)

> Curso: AdsPRO · Módulo 8 · PLATAFORMAS & AGENTES · ~6 min
> Formato: contenido a grabar (puntos a decir, no palabra por palabra).
> Voz: español colombiano, "tú", directa.
> Objetivo: que entiendan que no todas las plataformas sirven para lo mismo.

---

## 1. Hook
- Arranca directo: "Muchos negocios eligen mal la herramienta de WhatsApp y luego se quejan de que 'la IA no vende'. El problema casi nunca es la IA. Es que compraron una cosa para un trabajo que esa cosa no hace."
- Suelta el gancho: "Hoy te voy a mostrar los seis tipos de plataforma que existen. Cuando termines esta clase vas a poder mirar cualquier herramienta y saber en dos minutos si te sirve o te va a tocar cambiarla en tres meses."
- Marca la promesa: "Y de paso te abro por dentro un agente de IA para que veas de qué está hecho: el prompt, el handoff, el tono y cómo agrupa mensajes. Nada de magia."

## 2. Desarrollo (lo que cubres)

### Regla de oro: la plataforma se elige por el trabajo, no por la marca
- Deja clara la idea central: no existe "la mejor plataforma", existe la mejor plataforma para lo que TÚ necesitas hacer hoy.
- Adelanta que vas a recorrer seis tipos, de menos a más capacidad, y que cada uno resuelve un trabajo distinto y tiene un techo (un límite donde se queda corto).
- Pide que mientras avanzas piensen en la herramienta que usan hoy, para clasificarla al final.

### Tipo 1 — Bandeja simple (inbox)
- Qué es: una pantalla para leer y responder los WhatsApp a mano, ordenados por chat. Nada más.
- Para qué sirve: centralizar la conversación, que varias personas del equipo respondan sin pelearse el celular, y no perder mensajes.
- Su límite: todo es manual. Si no hay un humano escribiendo, no pasa nada. No filtra, no responde solo, no hace seguimiento.
- Para quién: negocio chiquito, pocos chats al día, todavía sin necesidad de automatizar.

### Tipo 2 — Automatización básica (reglas y disparadores)
- Qué es: la bandeja pero con reglas del tipo "si pasa esto, haz esto otro". Respuestas automáticas por palabra clave, mensaje de bienvenida, etiquetas automáticas.
- Para qué sirve: quitarte de encima lo repetitivo — horario, ubicación, "ya te contactamos", el saludo inicial.
- Su límite: es tonta. Solo hace lo que le programaste al pie de la letra. Si el cliente escribe distinto a lo que esperabas, se queda callada o responde cualquier cosa. No entiende, solo reacciona.
- Para quién: quien ya tiene volumen de preguntas repetidas y quiere responder rápido sin contratar más gente.

### Tipo 3 — Chatbot builder (flujos y botones)
- Qué es: una herramienta para armar conversaciones guiadas con menús, botones y árboles de decisión. Tú dibujas el flujo: "elige 1 para ventas, 2 para soporte".
- Para qué sirve: guiar al cliente por un proceso claro — tomar un pedido, calificar por pasos, agendar una cita con opciones cerradas.
- Su límite: el cliente tiene que seguir TU camino. Si se sale del guion, el bot se pierde. Conversación rígida, se siente robótico, y mantener flujos grandes se vuelve un enredo.
- Para quién: procesos que se pueden estandarizar en pasos, donde el cliente acepta ir por un menú.

### Tipo 4 — Agentes con IA (conversan de verdad)
- Qué es: un agente que entiende lenguaje natural. No necesitas botones: el cliente escribe como quiera y el agente responde con contexto, sostiene la conversación y puede consultar tu catálogo o tu CRM.
- Para qué sirve: atender y VENDER conversando — resolver dudas, recomendar producto, calificar, cerrar, y pasar a humano cuando toca. Es lo más cercano a un vendedor que no duerme.
- Su límite: hay que configurarlo bien (prompt, reglas, datos). Mal instruido, inventa o promete cosas. Y necesita datos conectados para no responder al aire.
- Para quién: negocios que venden por conversación y quieren volumen sin perder calidad ni tono.

### Tipo 5 — Todo-en-uno (plataforma de crecimiento)
- Qué es: el agente de IA + CRM + catálogo + campañas + seguimientos + métricas, todo en un mismo lugar y conectado.
- Para qué sirve: no solo responder, sino gestionar el ciclo completo — desde que entra el lead hasta la recompra — con la data en un solo tablero.
- Su límite: pagas por cosas que quizá no uses todavía, y tiene curva de aprendizaje. Si solo querías responder rápido, te queda grande.
- Para quién: negocio que ya vende por WhatsApp con volumen y quiere escalar ordenado, midiendo todo.

### Tipo 6 — Proveedor técnico (API / infraestructura)
- Qué es: el "ladrillo" de más abajo. Te dan acceso a la API de WhatsApp y tú (o tu desarrollador) construyes encima lo que quieras.
- Para qué sirve: control total y personalización máxima — integrar WhatsApp a un sistema propio, un flujo muy particular, cosas a la medida.
- Su límite: no sirve para el dueño de negocio solo. Necesitas equipo técnico. Sin desarrollador, no tienes nada usable.
- Para quién: empresas con área de tecnología o agencias que le montan la solución a otros.

### Los agentes de IA por dentro (los 4 componentes que sí importan)
- El prompt: son las instrucciones del agente. Quién es, qué vende, qué puede prometer y qué no, cómo responde. Aquí se gana o se pierde: un buen prompt convierte, uno flojo inventa. Es lo que más vas a ajustar.
- El handoff a humano: la regla de cuándo el agente suelta la conversación y avisa a una persona. Ejemplo: cliente molesto, caso raro, o pide hablar con alguien. Un agente sin handoff bien puesto te quema clientes.
- El tono humano: que suene a persona, no a robot. Frases cortas, natural, sin sonar acartonado ni sobreactuado. El tono lo defines tú en el prompt y hace toda la diferencia en la sensación del cliente.
- Agrupar mensajes (debounce): la gente escribe en pedacitos — "hola" / "quiero info" / "del producto azul". Si el agente responde a cada pedacito, se atropella. El debounce hace que espere un momentico, junte los mensajes y responda una sola vez, como respondería una persona.

## 3. Demo / Práctica
- Práctica en vivo: pon en pantalla 4 o 5 herramientas conocidas (las que use la audiencia) y clasifícalas en voz alta según el tipo — bandeja, automatización básica, builder, agente IA, todo-en-uno o proveedor técnico.
- Por cada una, di en una frase para qué sirve y cuál es su techo. Ejemplo del ejercicio: "esta es un builder, sirve para flujos con botones, pero si el cliente se sale del menú se pierde".
- Reta a la audiencia: "toma la herramienta que usas hoy, escríbele el tipo al lado y su límite. Si el límite ya te está estorbando, esa es la señal de que te toca subir de tipo."
- Cierra la práctica mostrando por dentro un agente de IA: señala dónde va el prompt, dónde se configura el handoff, dónde el tono y dónde se activa el debounce.

## 4. Cierre + puente al siguiente módulo
- Remata la idea: no compres por marca ni por precio, compra por el trabajo que necesitas hacer y por el techo que puedes aguantar. La plataforma correcta es la que te sirve hoy y aguanta a dónde vas.
- Refuerza: ya sabes que un agente de IA no es magia — es prompt, handoff, tono y debounce bien puestos.
- Puente: "Ya entiendes qué tipo de plataforma necesitas y qué tiene un agente por dentro. En el siguiente módulo lo aterrizamos en herramientas reales: arrancamos con Kommo, un CRM conversacional. Nos vemos allá."
