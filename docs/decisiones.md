# Registro de Decisiones de Maquetado Semántico

## 1. Uso de table y th scope="col" para el listado de tickets
**Elegido:** Se utilizó una estructura de `<table>` con elementos `<th>` definidos con `scope="col"` y `scope="row"`.
**Descartado:** Contenedores `<div>` simulando filas o una lista desordenada `<ul>`.
**Consecuencia que evita:** Permite a los usuarios de lectores de pantalla navegar por celdas escuchando la asociación directa entre el encabezado de columna y su valor (ej. "Estado: Abierto" en vez de solo "Abierto").

## 2. Asociación estricta de formularios con label y for
**Elegido:** Uso de elementos `<label>` vinculados explícitamente a los `<select>` e `<input>` mediante el atributo `for` e `id` idénticos.
**Descartado:** Campos de entrada sueltos con texto al lado en etiquetas `<span>`.
**Consecuencia que evita:** Evita que el lector de pantalla anuncie simplemente "cuadro de texto" o "menú desplegable" sin indicar qué dato se espera ingresar o seleccionar.

## 3. Navegación en el pie mediante footer y marca de tiempo con time
**Elegido:** Contenedor `<footer>` con bloques `<p>` y la hora dentro de `<time datetime="2026-09-11T09:40">`.
**Descartado:** Un `<div class="footer">` con texto corrido.
**Consecuencia que evita:** El elemento `footer` se anuncia automáticamente como región de pie de página permitiendo saltos directos mediante teclado; `<time>` deja la fecha comprensible para motores de búsqueda y lectores.