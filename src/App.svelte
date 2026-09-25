<script lang="ts">
  import Formulario from './Formulario.svelte'

  type Order = {
    number: number
    deliveryDate: string
    deliveryTime: string
    bouquetSize: string
    flowers: string
    recipient: string
    status: string
  }

  let orders: Order[] = [
    { number: 104, deliveryDate: '2026-09-18', deliveryTime: '10:30', bouquetSize: 'Mediano', flowers: 'rosas rojas', recipient: 'Tarqui', status: 'En preparación' },
    { number: 105, deliveryDate: '2026-09-18', deliveryTime: '12:00', bouquetSize: 'Grande', flowers: 'rosas rosadas y follaje', recipient: 'Los Esteros', status: 'Confirmado' },
    { number: 106, deliveryDate: '2026-09-18', deliveryTime: '15:30', bouquetSize: 'Pequeño', flowers: 'rosas blancas', recipient: 'Retiro en local', status: 'Recibido' },
  ]

  function addOrder(order: Omit<Order, 'number' | 'status'>) {
    orders = [
      ...orders,
      {
        ...order,
        number: Math.max(...orders.map((item) => item.number)) + 1,
        status: 'Recibido',
      },
    ]
  }

  function formatDelivery(date: string, time: string) {
    const delivery = new Date(`${date}T${time}`)
    return `${delivery.toLocaleDateString('es-EC', { day: 'numeric', month: 'short' })} · ${time}`
  }
</script>

<header class="site-header">
  <p class="brand"><strong>Roses Lolas</strong></p>
  <nav aria-label="Navegación principal">
    <ul>
      <li><a href="#pedidos">Pedidos</a></li>
      <li><a href="#nuevo-pedido">Nuevo pedido</a></li>
    </ul>
  </nav>
</header>

<main>
  <h1>Pedidos por preparar</h1>
  <p>Florista: pedidos ordenados por la hora de entrega comprometida.</p>

  <section id="pedidos" aria-labelledby="titulo-hoy">
    <h2 id="titulo-hoy">Para hoy</h2>
    <div class="tabla-scroll">
      <table>
        <caption>Pedidos que la florista debe preparar hoy</caption>
        <thead>
          <tr>
            <th scope="col">N.º de pedido</th>
            <th scope="col">Entrega</th>
            <th scope="col">Ramo</th>
            <th scope="col">Entrega a / zona</th>
            <th scope="col">Estado</th>
          </tr>
        </thead>
        <tbody>
          {#each orders as order}
            <tr>
              <th scope="row">{order.number}</th>
              <td><time datetime={`${order.deliveryDate}T${order.deliveryTime}`}>{formatDelivery(order.deliveryDate, order.deliveryTime)}</time></td>
              <td>{order.bouquetSize} · {order.flowers}</td>
              <td>{order.recipient}</td>
              <td>{order.status}</td>
            </tr>
          {/each}
        </tbody>
      </table>
    </div>
  </section>

  <Formulario onCreate={addOrder} />
</main>

<footer>
  <p><strong>Roses Lolas</strong> · Florería con armado de ramos a pedido</p>
  <p>Contacto · lunes a sábado, 08:00 a 18:00</p>
</footer>

