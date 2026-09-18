# Nuestro negocio

Negocio: Roses Lolas, florería con armado de ramos a pedido.
Video de Starter Story: pendiente de completar con el enlace de referencia usado por la pareja.
Como lo adaptamos a Ecuador: se consideran entregas locales, pagos disponibles en Ecuador y coordinación de horarios con la florista.

## Las dos entidades

1. Pedido
2. Ramo, que se relaciona con el pedido porque cada pedido contiene un ramo configurado con flores, follaje, papel, listón y extras.

## La entidad que cambia de estado

Entidad: Pedido
Estados: recibido -> confirmado -> en preparación -> listo -> entregado; también puede terminar en cancelado.
Quien provoca cada cambio: el cliente crea el pedido en recibido; la florista lo confirma, lo prepara y lo marca como listo y entregado. El cliente puede cancelarlo mientras esté recibido.

## Los dos roles

- Cliente comprador: puede configurar un ramo, crear pedidos y consultar sus propios pedidos; no puede ver ni cambiar pedidos de otros clientes ni marcar estados de preparación.
- Florista: puede consultar todos los pedidos y cambiar su estado durante la preparación y entrega; no puede cambiar la configuración del ramo solicitada por el cliente.

## La pantalla de hoy

El rol que la usa: Florista.
La pregunta que responde: ¿Qué ramos tengo que armar hoy, en qué orden, y cuáles ya están listos?

## Pendientes

- Completar el enlace exacto del video de Starter Story usado como referencia.
- Confirmar si el cliente también puede cancelar un pedido en estado confirmado.