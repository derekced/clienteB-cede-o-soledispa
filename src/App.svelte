<header>
  <p><strong>Mesa de Ayuda</strong></p>
  <nav aria-label="Navegación principal">
    <ul>
      <li><a href="/tickets">Tickets</a></li>
      <li><a href="/clientes">Clientes</a></li>
      <li><a href="/reportes">Reportes</a></li>
    </ul>
  </nav>
  <a href="/tickets/nuevo">Nuevo ticket</a>
</header>

<main>
  <h1>Bandeja de tickets</h1>
  <p>Agente: Mariela Zambrano | 6 tickets asignados</p>

  <section aria-labelledby="titulo-filtros">
    <h2 id="titulo-filtros">Filtros</h2>
    <form>
      <div>
        <label for="filtro-estado">Estado:</label>
        <select id="filtro-estado" name="estado">
          <option value="todos">Todos</option>
          <option value="abierto">Abierto</option>
          <option value="en_progreso">En progreso</option>
          <option value="en_espera">En espera</option>
          <option value="resuelto">Resuelto</option>
          <option value="cerrado">Cerrado</option>
        </select>
      </div>

      <div>
        <label for="filtro-prioridad">Prioridad:</label>
        <select id="filtro-prioridad" name="prioridad">
          <option value="todas">Todas</option>
          <option value="alta">Alta</option>
          <option value="media">Media</option>
          <option value="baja">Baja</option>
        </select>
      </div>

      <div>
        <label for="buscar-texto">Buscar:</label>
        <input type="text" id="buscar-texto" name="buscar" placeholder="Asunto o cliente" />
      </div>

      <button type="submit">Aplicar filtros</button>
    </form>
  </section>

  <section aria-labelledby="titulo-resumen">
    <h2 id="titulo-resumen">Resumen</h2>
    <dl>
      <dt>Abiertos:</dt>
      <dd>2</dd>
      <dt>En progreso:</dt>
      <dd>2</dd>
      <dt>En espera:</dt>
      <dd>1</dd>
      <dt>Resueltos:</dt>
      <dd>1</dd>
    </dl>
  </section>

  <section aria-labelledby="titulo-listado">
    <h2 id="titulo-listado">Listado de tickets</h2>
    <table>
      <caption>Tickets asignados al agente</caption>
      <thead>
        <tr>
          <th scope="col">N.º</th>
          <th scope="col">Asunto</th>
          <th scope="col">Cliente</th>
          <th scope="col">Estado</th>
          <th scope="col">Prioridad</th>
          <th scope="col">Última actualización</th>
          <th scope="col">Acción</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th scope="row">1041</th>
          <td>No puedo iniciar sesión en el portal</td>
          <td>Comercial Vélez</td>
          <td>Abierto</td>
          <td>Alta</td>
          <td><time datetime="PT20M">hace 20 min</time></td>
          <td><a href="/tickets/1041">Ver</a></td>
        </tr>
        <tr>
          <th scope="row">1038</th>
          <td>La factura electrónica no llega al correo</td>
          <td>Ferretería El Progreso</td>
          <td>En progreso</td>
          <td>Media</td>
          <td><time datetime="PT2H">hace 2 h</time></td>
          <td><a href="/tickets/1038">Ver</a></td>
        </tr>
        <tr>
          <th scope="row">1035</th>
          <td>Error al exportar el reporte mensual</td>
          <td>Distribuidora Manabí</td>
          <td>En espera</td>
          <td>Media</td>
          <td><time datetime="P1D">ayer</time></td>
          <td><a href="/tickets/1035">Ver</a></td>
        </tr>
        <tr>
          <th scope="row">1031</th>
          <td>Solicitud de un usuario adicional</td>
          <td>Clínica San Rafael</td>
          <td>Abierto</td>
          <td>Baja</td>
          <td><time datetime="P1D">ayer</time></td>
          <td><a href="/tickets/1031">Ver</a></td>
        </tr>
        <tr>
          <th scope="row">1027</th>
          <td>Lentitud al cargar el inventario</td>
          <td>Comercial Vélez</td>
          <td>En progreso</td>
          <td>Alta</td>
          <td><time datetime="P3D">hace 3 días</time></td>
          <td><a href="/tickets/1027">Ver</a></td>
        </tr>
        <tr>
          <th scope="row">1019</th>
          <td>Cambio de RUC en la cuenta</td>
          <td>Panadería Doña Luz</td>
          <td>Resuelto</td>
          <td>Baja</td>
          <td><time datetime="P5D">hace 5 días</time></td>
          <td><a href="/tickets/1019">Ver</a></td>
        </tr>
      </tbody>
    </table>
  </section>
</main>

<footer>
  <p>Mesa de Ayuda</p>
  <p>Proyecto docente 2026-2</p>
  <p>Última sincronización: <time datetime="2026-09-11T09:40">hoy, 09:40</time></p>
</footer>
