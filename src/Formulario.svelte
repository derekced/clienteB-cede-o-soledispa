<section id="nuevo-pedido" class="form-section" aria-labelledby="titulo-formulario">
  <div class="section-heading">
    <div>
      <p class="eyebrow">Cliente comprador</p>
      <h2 id="titulo-formulario">Nuevo pedido</h2>
    </div>
    <p class="state-note">Estado inicial: <strong>Recibido</strong></p>
  </div>

  <form onsubmit={handleSubmit}>
    <div class="form-grid">
      <div class="form-field">
        <label for="tamano-ramo">Tamaño del ramo</label>
        <select bind:value={formData.bouquetSize} id="tamano-ramo" name="tamano-ramo" required aria-invalid={!hasBouquetSize} aria-describedby={hasBouquetSize ? undefined : 'tamano-ramo-error'}>
          <option value="" selected disabled>Selecciona un tamaño</option>
          <option>Pequeño</option>
          <option>Mediano</option>
          <option>Grande</option>
        </select>
        {#if !hasBouquetSize}<p id="tamano-ramo-error" class="error-message">Error: selecciona el tamaño del ramo.</p>{/if}
      </div>

      <div class="form-field">
        <label for="flores-follaje">Flores y follaje</label>
        <input bind:value={formData.flowers} type="text" id="flores-follaje" name="flores-follaje" placeholder="Ej.: rosas rojas y eucalipto" required aria-invalid={!hasFlowers} aria-describedby={hasFlowers ? undefined : 'flores-follaje-error'} />
        {#if !hasFlowers}<p id="flores-follaje-error" class="error-message">Error: escribe las flores y el follaje.</p>{/if}
      </div>

      <div class="form-field">
        <fieldset class="date-time-field">
          <legend>Fecha y hora de entrega</legend>
          <div class="date-time-inputs">
            <label for="fecha-entrega">Fecha</label>
            <label for="hora-entrega">Hora</label>
            <input bind:value={formData.deliveryDate} type="date" id="fecha-entrega" name="fecha-entrega" required aria-invalid={!hasDelivery} aria-describedby={hasDelivery ? undefined : 'fecha-entrega-error'} />
            <input bind:value={formData.deliveryTime} type="time" id="hora-entrega" name="hora-entrega" required aria-invalid={!hasDelivery} aria-describedby={hasDelivery ? undefined : 'fecha-entrega-error'} />
          </div>
        </fieldset>
        {#if !hasDelivery}<p id="fecha-entrega-error" class="error-message">Error: indica la fecha y hora de entrega.</p>{/if}
      </div>

      <div class="form-field">
        <label for="entrega-zona">Entrega a / zona</label>
        <input bind:value={formData.recipient} type="text" id="entrega-zona" name="entrega-zona" placeholder="Ej.: Ana · Tarqui" required aria-invalid={!hasRecipient} aria-describedby={hasRecipient ? undefined : 'entrega-zona-error'} />
        {#if !hasRecipient}<p id="entrega-zona-error" class="error-message">Error: escribe el destinatario y la zona.</p>{/if}
      </div>

      <div class="form-field">
        <label for="forma-pago">Forma de pago</label>
        <select bind:value={formData.payment} id="forma-pago" name="forma-pago" required aria-invalid={!hasPayment} aria-describedby={hasPayment ? undefined : 'forma-pago-error'}>
          <option value="" selected disabled>Selecciona una forma</option>
          <option>Transferencia bancaria</option>
          <option>Pago en efectivo</option>
          <option>Tarjeta</option>
        </select>
        {#if !hasPayment}<p id="forma-pago-error" class="error-message">Error: selecciona una forma de pago.</p>{/if}
      </div>
    </div>

    <button type="submit">Crear pedido</button>
    {#if submitted}<p class="success-message" role="status">Pedido agregado a la tabla con estado Recibido.</p>{/if}
  </form>
</section>

<script lang="ts">
  export let onCreate: (order: {
    deliveryDate: string
    deliveryTime: string
    bouquetSize: string
    flowers: string
    recipient: string
  }) => void

  let formData = {
    bouquetSize: '',
    flowers: '',
    deliveryDate: '',
    deliveryTime: '',
    recipient: '',
    payment: '',
  }

  $: hasBouquetSize = Boolean(formData.bouquetSize)
  $: hasFlowers = Boolean(formData.flowers.trim())
  $: hasDelivery = Boolean(formData.deliveryDate && formData.deliveryTime)
  $: hasRecipient = Boolean(formData.recipient.trim())
  $: hasPayment = Boolean(formData.payment)
  let submitted = false

  function handleSubmit(event: SubmitEvent) {
    event.preventDefault()
    onCreate({
      deliveryDate: formData.deliveryDate,
      deliveryTime: formData.deliveryTime,
      bouquetSize: formData.bouquetSize,
      flowers: formData.flowers.trim(),
      recipient: formData.recipient.trim(),
    })
    submitted = true
  }
</script>
