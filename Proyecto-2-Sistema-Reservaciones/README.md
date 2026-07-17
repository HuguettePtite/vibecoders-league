# Proyecto 2: Tu producto en línea, capturando datos reales (Due Terre)
![Due Terre Trattoria](due-terre-trattoria.png)

## 📌 El Reto de la Liga
El objetivo de este segundo módulo en la VibeCoders League consistió en evolucionar una interfaz estática hacia un **sistema web funcional** capaz de capturar e interactuar con información en tiempo real. La meta técnica: conectar un formulario real a una base de datos persistente (Supabase) evitando "botones decorativos".

## 🛠️ Implementación y Eficiencia con Vibe Coding
Demostrando la velocidad y potencia del desarrollo guiado por IA, la migración completa del backend, la base de datos y los componentes responsivos del frontend se logró utilizando **un único Prompt Maestro** y activando la infraestructura integrada de Supabase.

### 🗄️ Estructura del Backend (Supabase)
Se diseñó un modelo de datos limpio y estricto en la tabla relacional `reservaciones` con los siguientes atributos:
*   `id` (UUID / Llave Primaria) - Generado automáticamente por el sistema.
*   `nombre` (Text) - Nombre completo de quien reserva.
*   `correo` (Text) - Correo electrónico de contacto.
*   `invitados` (Integer) - Cantidad de comensales.
*   `fecha_hora` (Timestampz) - Zona horaria y fecha de la cita en Coyoacán.
*   `club_vinos` (Boolean) - Estado de suscripción al Club de Fidelidad.

---
## 📺 Demostración del Sistema en Tiempo Real

A continuación, se muestra una grabación de pantalla con el registro en la base de datos de Supabase:

https://github.com/user-attachments/assets/4d7b478c-d28c-447d-ab09-5d7796e7340e


## 💡 Innovación en la Experiencia de Usuario (UX)
En lugar de añadir un formulario de contacto frío y genérico, se fusionaron dos necesidades del negocio bajo una atmósfera sofisticada acorde al entorno tradicional de Coyoacán:

1.  **Reservación Elegante:** Un componente frontend responsivo (adaptado a PC y móviles) integrado al diseño rústico-moderno que permite apartar una mesa en el local.
2.  **L'Impronta Italiana (Club Due Terre):** Un checkbox estético antes de confirmar la reserva que invita voluntariamente a los comensales a unirse al Club de Vinos para recibir invitaciones a catas exclusivas en alianza con la importadora *Il Porto d'Italia*.

---

## 🧠 Evolución de Gianluca (IA Conversacional)
El asistente de IA fue re-entrenado para comprender esta actualización del sistema. Ahora, cuando un comensal menciona intenciones de asistir o reservar una mesa en el chat, Gianluca lo redirige con total naturalidad hacia la sección interactiva del formulario web, cerrando un flujo de usuario impecable.

## 🔗 Enlace de Producción
👉 [Prueba el prototipo en vivo aquí](https://dueterre-trattoria.lovable.app) 

## 📝 Ingeniería de Prompts (Prompt Engineering)

<details>
<summary><b>⚙️ Ver el Prompt Maestro de Conexión y Backend (Proyecto 2)</b></summary>

```text
Captura de datos reales con Supabase. Por favor, realiza las siguientes implementaciones frontend y de backend:

1. CREACIÓN DE LA TABLA EN SUPABASE:
- Crea una tabla en Supabase llamada "reservaciones" con los siguientes campos exactos:
  * nombre (text)
  * correo (text)
  * invitados (integer)
  * fecha_hora (timestampz)
  * club_vinos (boolean)

2. DISEÑO DEL FORMULARIO DE RESERVACIÓN ELEGANTE:
- Diseña una sección nueva en la página web dedicada exclusivamente a "Reservaciones".
- El estilo debe ser rústico-moderno y muy elegante, usando nuestra paleta de tonos crema y verde oliva profundo.
- Incluye campos limpios y responsivos para: Nombre Completo, Correo Electrónico, Número de Invitados, y Fecha/Hora de la reserva.
- Justo antes del botón de confirmación, añade un checkbox estético que diga: "Deseo unirme al Club Due Terre para recibir invitaciones a catas exclusivas y recomendaciones de vinos importados por Il Porto d'Italia."
- Configura el botón para que, al hacer clic, guarde los datos directamente en la tabla de Supabase en tiempo real y muestre un mensaje de éxito muy hospitalario.

3. CONEXIÓN CON GIANLUCA (EL ASISTENTE DE IA):
- Actualiza el conocimiento y comportamiento de Gianluca. Ahora, cuando un usuario interactúe en el chat y mencione que desea hacer una reservación, Gianluca debe guiarlo amablemente hacia esta nueva sección de la página o indicarle que puede llenar el formulario directamente en la web para asegurar su lugar.
```
</details>
