# Product Management Examples

This document provides examples of how to perform CRUD operations on products using the Freemius API.

## Create a Product

Example of creating a new product:

```bash
curl -X POST "https://api.freemius.com/v1/products.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
           "name": "New Product",
           "type": "plugin",
           "secret_key": "sk_a1b2c3d4e5f6g7h8i9j0k1l2m3n4o5p6"
         }'
```

## Retrieve a Product

Example of retrieving product details:

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## Update a Product

Example of updating product information:

```bash
curl -X PUT "https://api.freemius.com/v1/products/{product_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
           "name": "Updated Product Name"
         }'
```

## Delete a Product

Example of deleting a product:

```bash
curl -X DELETE "https://api.freemius.com/v1/products/{product_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

Replace `{product_id}` with the actual product ID and `YOUR_API_KEY` with your API key in the examples above.
