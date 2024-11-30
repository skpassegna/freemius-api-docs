# Payment Processing Examples

This document provides examples of handling payments using the Freemius API.

## Retrieve Payment Details

Example of retrieving details of a specific payment:

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/payments/{payment_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## List Payments

Example of listing all payments associated with a product:

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/payments.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## Process Refund

Example of processing a refund for a payment:

```bash
curl -X POST "https://api.freemius.com/v1/products/{product_id}/payments/{payment_id}/refund.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
           "amount": "10.00",
           "currency": "USD"
         }'
```

## Handle Payment Dispute

Example of handling a payment dispute:

```bash
curl -X POST "https://api.freemius.com/v1/products/{product_id}/payments/{payment_id}/dispute.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
           "reason": "fraudulent"
         }'
```

Replace `{product_id}`, `{payment_id}`, and `YOUR_API_KEY` with the actual product ID, payment ID, and your API key in the examples above.
