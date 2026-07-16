# Proyecto 3: Captura creativa de leads mediante gamificación (Due Terre)

## 📌 El Reto de la Liga
El objetivo de este tercer módulo en la VibeCoders League fue romper con la monotonía de los formularios tradicionales de contacto. El desafío consistió en diseñar una **herramienta interactiva y gamificada** que ofreciera un valor real, lúdico o educativo al usuario *antes* de solicitar sus datos, logrando así un intercambio orgánico, sofisticado y de alta conversión.

## 🍷 Propuesta e Innovación: "El Alma Gemela del Vino"
En lugar de recolectar correos de forma fría, el sistema transporta al usuario a la atmósfera tradicional de Coyoacán a través de una experiencia interactiva:

1.  **El Quiz de Personalidad (Gamificación):** Un cuestionario dinámico de 3 preguntas estilizadas que analiza los gustos, estilos de vida y preferencias del usuario para determinar qué vino de nuestra reserva es su "alma gemela".
2.  **La Recompensa (Fidelity Card Digital):** Tras completar el test, el usuario introduce su nombre y correo. Al instante, los datos se procesan y la interfaz genera de forma dinámica una **Tarjeta de Fidelidad del Club Due Terre** personalizada con su nombre, su vino asignado (ej. *Chianti Classico, Pinot Grigio, Barolo*) y un código QR estético de miembro.
3.  **Alianza Estratégica:** Esta captura se conecta con los beneficios exclusivos y catas organizadas en conjunto con la importadora *Il Porto d'Italia*.

---

## 🛠️ Optimización Técnica y Eficiencia de Recursos
Con el fin de mantener un desarrollo ágil y optimizar el procesamiento del backend, se implementaron soluciones arquitectónicas muy precisas:

*   **Persistencia en Tiempo Real:** Los datos del perfil del usuario y el resultado exacto de su quiz se almacenan de forma asíncrona en la tabla relacional `club_fidelidad` en Supabase.
*   **Manejo del Estado Asíncrono:** Se corrigió el flujo de renderizado mediante promesas para asegurar que la tarjeta digital solo se muestre en pantalla una vez que Supabase confirme la inserción exitosa del registro, evitando errores de sincronización.
*   **Guardado en PDF Ultra-Eficiente:** En lugar de saturar el backend con pesadas librerías de generación de archivos o automatizaciones de correo, se diseñó un botón interactivo "Guardar Tarjeta" que invoca la función nativa `window.print()`. Esto permite al usuario descargar su pase exclusivo como **PDF** o imprimirlo directamente usando los recursos del propio navegador.

---

## 🧠 Optimización de UX y Gianluca
Basado en el valioso feedback de los usuarios, se realizaron dos grandes mejoras en la experiencia conversacional:
*   **Rediseño de Interfaz:** Se incrementó la escala y visibilidad del botón flotante del asistente virtual (Gianluca) para evitar que fuera obstruido por elementos del editor, mejorando significativamente el *Click-Through Rate* (CTR) sin romper la hermosa estética rústica-moderna.
*   **Inteligencia Conversacional:** Se entrenó el contexto de Gianluca para que, al detectar dudas sobre eventos, catas o promociones, invite proactivamente al usuario a realizar el Quiz en la web para obtener su tarjeta de fidelidad.

## 📝 Ingeniería de Prompts (Prompt Engineering)

<details>
<summary><b>⚙️ Ver el Prompt Maestro de Gamificación e Interactividad (Proyecto 3)</b></summary>

```text
Captura creativa de leads.
Diseña una herramienta interactiva y gamificada basada en un "Quiz de Personalidad del Vino" conectado a una base de datos, y mejora la visibilidad de nuestro asistente.

1. CREACIÓN DE LA TABLA EN EL BACKEND:
- Crea una tabla llamada "club_fidelidad" con los campos: nombre (text), correo (text), resultado_quiz (text).

2. DISEÑO DEL QUIZ INTERACTIVO (FRONTEND):
- Añade una sección elegante y rústica llamada "El Alma Gemela del Vino".
- Diseña un cuestionario dinámico de 3 preguntas con opciones visuales atractivas sobre gustos y estilos de vida.
- Al terminar las preguntas, muestra una pantalla de transición que invite al usuario a ingresar su Nombre y Correo para generar su Tarjeta Digital de Fidelidad del Club Due Terre y recibir beneficios y catas exclusivas de la mano de Il Porto d'Italia.

3. LA TARJETA DE FIDELIDAD DIGITAL:
- Cuando el usuario envíe el formulario, guarda los datos en la tabla "club_fidelidad" en tiempo real.
- Inmediatamente después, muestra una tarjeta digital (Fidelity Card) flotante, minimalista y hermosa con tipografía Serif sofisticada, que muestre de forma dinámica el Nombre del usuario, el Vino asignado según sus respuestas (ej. Chianti Classico, Pinot Grigio, Barolo) y un código QR estético de miembro del club.
- Añade un botón estético y minimalista dentro de la Tarjeta de Fidelidad que diga "Guardar Tarjeta". Al hacer clic, debe ejecutar la función nativa window.print() o aplicar un estilo CSS de impresión simple para que el usuario pueda guardarla fácilmente como PDF desde su navegador sin configuraciones pesadas de backend.

4. ACTUALIZACIÓN DE GIANLUCA Y AJUSTE DE TAMAÑO DEL BOTÓN:
- MANTÉN EL DISEÑO ACTUAL DEL BOTÓN DEL CHAT (conserva los colores, la estructura, el texto "Habla con Gianluca / Asistente virtual", el icono y el avatar del chef).
- Haz que el botón sea significativamente más grande en escala para mejorar su visibilidad.
- Ajusta su posición vertical (mantenlo abajo a la derecha, pero súbelo unos píxeles más) para que la etiqueta flotante de "Edit with Lovable" no lo obstruya ni lo tape visualmente.
- Entrena el conocimiento de Gianluca para que, si alguien le pregunta por catas, promociones o el club de vinos, los invite con entusiasmo a realizar el nuevo Quiz en la página web para descubrir su vino ideal y obtener su tarjeta digital de fidelidad.

PROMPT 2
Corrige el bug al generar la tarjeta de fidelidad: el mensaje "no pudimos generar tu tarjeta" ocurre porque la interfaz intenta mostrar la tarjeta antes de que Supabase confirme la inserción del lead. Ajusta el flujo para que espere la respuesta exitosa de Supabase de forma asíncrona, guarde el id y el resultado del quiz en el estado local, y luego renderice la tarjeta digital con los datos correspondientes sin lanzar el error.

PROMPT 3
Por favor, realiza los siguientes dos ajustes específicos de UI/UX en el proyecto para corregir inconsistencias y añadir funcionalidad:

1. UNIFICACIÓN DE TEXTOS (EL ALMA GEMELA DEL VINO):
- Corrige el nombre en el header de esta sección. Actualmente dice "El Club del Vino", por favor cámbialo para que diga exactamente "El Alma Gemela del Vino".
- Asegúrate de que tanto en el header como en el contenido principal (main) se utilice de forma consistente el nombre correcto: "El Alma Gemela del Vino".

2. BOTÓN DE GUARDADO NATIVO EN LA TARJETA:
- Dentro del componente visual de la Tarjeta de Fidelidad (Fidelity Card) que se muestra al finalizar el quiz, añade un botón estético, limpio y minimalista que diga "Guardar Tarjeta".
- Configura este botón para que, al hacer clic, ejecute de forma directa la función nativa del navegador window.print(). 
- Asegúrate de que aplique un estilo CSS de impresión básico (@media print) para que el usuario pueda guardar la tarjeta cómodamente como PDF o imprimirla desde su dispositivo de manera limpia, ocultando el resto de la página web durante la impresión.
```
</details>
