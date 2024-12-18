# Payin

This features allows Yativo user's top up their account or their end user's by passing the customer ID in the object.

to make a deposit first of all get the payment currencies available for the deposit currency via a get request to&#x20;

> ```
> GET /payment-methods/payin/currency?country={GBR}
> ```

Then use get the available payment gateways using the Country and Currency as Parameters &#x20;

```
GET /payment-methods/payin?country=chl&currency=clp
```

Then make a Post request&#x20;

<pre><code><strong>POST /wallet/deposits/new
</strong><strong>
</strong>{
    "gateway": 235,
    "amount": 109,
    "currency": "USD"
    // "customer_id": "845a0c7a-33ae-4449-9239-76d0803aadbc"
}
</code></pre>
