# Deliveries and Payments

Companies get paid whenever their vehicles unload cargo at a station 
that accepts it. The payment depends on:

- The type of cargo

- The time the delivery took

- The amount delivered

- The distance between the source and destrination

Each cargo type differs in both the maximum payment rate and the rate 
that cargo payments decline. For example, steel pays more than coal or 
iron ore. All three cargos decay slowly and still pay most of their 
original value after 120 days. Passengers pays more than other cargo 
types at first. However, they 'decay' very quickly and will pay nothing 
if the transport takes more than 88 days.

One is paid in proportion to both the amount delivered and the distance 
of the delivery.

> [!TIP]
>
> You choose where your routes will deliver cargo. It is generally more 
> profitable to transport cargo between more distant destinations, 
> provided the delivery is reasonably fast.

Ignoring inflation, the payment \\( p \\) for delivering \\( m \\) units 
of cargo of type \\( c \\) a distance of \\( d \\) tiles in \\( t \\) 
days is:

\\[ p = r(c, t) \times m \times d \\]

Where \\( r(c, t) \\) is the unit payment rate for delivering \\( c \\) in 
\\( t \\) days. The exact formula can be found in 
CompanyManager::calculateDeliveredCargoPayment() in CompanyManager.cpp.

To see what the payment rates are, consult the 'Cargo Payment Rates' tab 
(the second from the right) of the charts window. It shows the payment 
for transporting 100 units of cargo 10 tiles.
