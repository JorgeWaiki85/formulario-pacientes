# Formulario de Atención de Pacientes

Formulario web pensado para completar **desde el celular** durante la atención de un paciente.
Funciona sin instalación y sin servidor: todo está en un solo archivo (`index.html`).

## Cómo usarlo

1. Abre `index.html` en el navegador (doble clic en el computador).
2. En el celular, publícalo en cualquier hosting gratuito con HTTPS y ábrelo desde el navegador.
   - **Netlify Drop:** https://app.netlify.com/drop (arrastra la carpeta completa).
   - **GitHub Pages:** sube la carpeta a un repositorio y activa Pages.
   - **Vercel / Cloudflare Pages:** publica la carpeta como sitio estático.
3. Opcional: desde Chrome (Android) o Safari (iPhone), usa “Agregar a pantalla de inicio”.

## Funciones incluidas

- **Nuevo paciente:** registra automáticamente la fecha y la hora actuales y limpia el formulario.
- **Datos del paciente:** nombre, edad, RUN y colegio.
- **Menor de edad (SI/NO):** al elegir SI se habilitan los campos de contacto de emergencia.
- **Signos vitales:** P.A, FC, FR, SAT, HGT y T°.
  - El botón **“+ Nueva toma de signos vitales”** agrega otra toma y le asigna la hora automáticamente.
  - Cada toma se puede eliminar (queda siempre una).
- **Alergias (SI/NO):** al elegir SI se habilita el detalle de la alergia.
- **Motivo de la consulta y tratamiento:** campos de texto libre.
- **Traslado (SI/NO):** al elegir SI se habilitan lugar de traslado, ambulancia y a cargo de.
- **Borrador automático:** si se cierra o recarga la página, los datos se recuperan en el mismo dispositivo.
- **Vista previa:** muestra el informe tal como se enviará (títulos y rótulos en negrita, datos normales).
- **Enviar por WhatsApp:** abre WhatsApp con el informe listo para elegir el contacto.

## Reglas del informe

- Los títulos y rótulos van **en negrita** usando el formato de WhatsApp; los datos escritos en los campos se envían sin negrita.
- Las unidades se agregan solas:
  - FC: `(x min)`
  - FR: `(x min)`
  - SAT: `(% ambiente)`
  - HGT: `(mg/dl)`
  - T°: `(°)`
- Los campos que no se completan **no aparecen** en el informe.
- Cada toma de signos vitales incluye su propia hora; las tomas sin datos se omiten.
- Si “menor de edad” es NO, no se envía el bloque de contacto de emergencia.
- Si “alergias” es NO, solo se informa que no presenta alergias.
- Si “traslado” es NO, solo se informa que no se realizó traslado.

## Privacidad

No hay backend ni base de datos: los datos viven únicamente en el navegador del dispositivo
(borrador en `localStorage`) y se envían por WhatsApp cuando la persona lo decide.
Al usar “Nuevo paciente”, el borrador anterior se elimina.

## Compatibilidad

Probado en Chrome/Edge actuales y con diseño adaptable desde 320 px de ancho.
Para iPhone, abre el sitio en Safari; para Android, en Chrome.
