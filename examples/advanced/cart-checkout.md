# Cart and Checkout Process Examples

This document provides examples of managing the cart and checkout process using the Freemius API.

## Retrieve Cart Details

Example of retrieving details of a specific cart:

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/carts/{cart_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## List Carts

Example of listing all carts associated with a product:

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/carts.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## Enriched Cart Details

Example of retrieving enriched cart details:

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/carts/{cart_id}.json?enriched=true" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## Delete Cart

Example of deleting a cart:

```bash
curl -X DELETE "https://api.freemius.com/v1/products/{product_id}/carts/{cart_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

Replace `{product_id}`, `{cart_id}`, and `YOUR_API_KEY` with the actual product ID, cart ID, and your API key in the examples above.
