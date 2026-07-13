# Proyecto 1: El asistente que responde por tu negocio (Due Terre Trattoria)

## 📌 El Problema Real
Due Terre es una trattoria artesanal real ubicada en la calle Malintzin, Coyoacán, con una excelente propuesta gastronómica pero una presencia digital que no reflejaba su esencia rústica y de barrio. Además, el negocio forma parte de la importadora *Il Porto d'Italia* (en Francisco Sosa), un vínculo comercial potente que no estaba visibilizado en sus canales digitales.

## 🛠️ Solución Implementada
Diseñé una interfaz web minimalista que integra a **Gianluca**, un asistente virtual de IA entrenado para resolver dudas de clientes en tiempo real sin salir de la página.

### 🧠 Base de Conocimiento de la IA (Knowledge Base)
El asistente cuenta con un marco contextual estricto de 10 datos clave:
1.  **Concepto:** Pastas frescas hechas a mano y pizzas de masa madre.
2.  **Ubicación Exacta:** Malintzin 165 local 2a, Col. Del Carmen, Coyoacán.
3.  **Alianza Estratégica:** Conexión explícita con la tienda *Il Porto d'Italia* (Av. Francisco Sosa 9, Coyoacán).
4.  **Horarios:** Martes a Sábado (13:00 a 22:00 h), Domingos (13:00 a 19:00 h). Lunes cerrado.
5.  **Platos del Menú Integrados:** Precios y especialidades extraídos directamente del menú en código.
6.  **Contacto Directo:** Correo `info@dueterre.shop` y WhatsApp corporativo.
7.  **Platos destacados:** Lasagna alla Bolognese clásica y Fettuccine artesanal.
8.  **Reservas:** Se recomiendan para los fines de semana a través de su enlace oficial de WhatsApp.
9.  **Métodos de pago:** Efectivo, transferencias bancarias y tarjetas de débito/crédito principales.
10.  **Fiestas y Eventos privados:** Ofrecemos el espacio de la trattoria para eventos privados, comidas corporativas o celebraciones íntimas. Contamos con menús de degustación personalizados. Para cotizaciones, el cliente debe escribir directamente a nuestro correo oficial.
11. **Servicio a domicilio (Delivery):** Due Terre Trattoria cuenta con servicio a domicilio a través de la plataforma Rappi para que disfruten de nuestras pastas frescas y pizzas de masa madre en casa. Si un usuario pregunta en el chat, Gianluca debe confirmar que operamos mediante Rappi, pero aclarar que los pedidos se gestionan directamente desde la app de Rappi y no tomamos pedidos de delivery por este chat.

### 🛡️ Políticas Anti-Alucinación y UX
*   **Control de Incertidumbre:** Si el usuario pregunta algo fuera de la base de conocimiento (como estacionamiento o promociones del día), la IA se disculpa amablemente en un tono hospitalario y activa dinámicamente un componente web con un botón interactivo.
*   **Enlace Seguro:** El botón utiliza JavaScript nativo para redirigir directamente al API oficial de WhatsApp con un mensaje pre-llenado de reserva, evitando que el cliente quede varado en un enlace roto.
*   **Mapas Desplegables:** Implementación de modales emergentes al hacer clic en el símbolo de GPS para geolocalizar ambos locales en Coyoacán de forma fluida.

## 🔗 Enlace de Producción
👉 [Prueba el prototipo en vivo aquí](https://dueterre-trattoria.lovable.app)
