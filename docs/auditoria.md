# Auditoría de accesibilidad — Semana 4

## 1. Lo que vio la herramienta

- Antes (listado de la semana 3): 100 / 100 · sin hallazgos automáticos.
- Con el formulario recién agregado, primera pasada: 100 / 100.
- Hallazgos y correcciones: los controles tienen etiquetas asociadas, el botón es un `button type="submit"`, el foco conserva su indicador visible y los objetivos táctiles tienen relleno.

## 2. Lo que no vio y cómo lo encontramos

- Barrera: el estado del pedido podía entenderse solo por color. A quién dejaba afuera: una persona que no distingue rojo de verde. Cómo la encontramos: leyendo el listado y comprobando que cada celda incluye la palabra del estado, además de cualquier color.
- Barrera: un mensaje de error puede existir visualmente sin que el lector de pantalla sepa a qué campo corresponde. A quién dejaba afuera: una persona que usa tecnología de apoyo para corregir el formulario. Cómo la encontramos: revisando el marcado y comprobando que cada `aria-describedby` coincide exactamente con el `id` del mensaje.
- Barrera: un formulario puede parecer usable con ratón y tener un orden de teclado confuso. A quién dejaba afuera: una persona que no usa el ratón. Cómo la encontramos: recorriendo los controles con Tab y comprobando que el orden sigue la lectura y termina en el botón.

## 3. Después

- Después: 100 / 100 · informe en `docs/auditoria_despues.html`.
- Informe inicial: `docs/auditoria_antes.html`.

## 4. La paleta

- Mensajes de error: `#8a2530` sobre `#fffdfc`; se eligió un rojo oscuro para que el error no dependa solo del color y conserve contraste suficiente.
- Estados y textos: se mantienen como palabras visibles en texto oscuro; el significado no depende del color.
