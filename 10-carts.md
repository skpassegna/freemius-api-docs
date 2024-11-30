# Carts

## Overview

According to the API specification, a cart represents a buyer's intent to purchase a product. The state of the cart is based on the action performed by the buyer.

## Cart Properties

Based on the API specification's Cart schema:

### Basic Information
- `id` - Unique identifier
- Cart state and status information
- Associated product and user information

### Enriched Properties
When using the enriched option, additional details are available:
- `gross` - Pricing information
- `coupon_code` - Applied coupon information
- `licenses` - License details

## API Endpoints

### Get Cart Details

```http
GET /products/{product_id}/carts/{cart_id}.json
```

Retrieves detailed information about a specific cart.

#### Parameters
- `product_id` (path) - The ID of the product
- `cart_id` (path) - The ID of the cart
- `enriched` (query) - Optional boolean parameter to get enriched cart details
- `fields` (query) - Optional parameter to specify which fields to return

### List Carts

```http
GET /products/{product_id}/carts.json
```

Retrieves a list of carts associated with a product.

### Delete Cart

```http
DELETE /products/{product_id}/carts/{cart_id}.json
```

Deletes a specific cart.

## Cart Management

### Cart States
Carts can be in different states based on buyer actions:
- Initial creation
- Checkout process
- Completion or abandonment

### Cart Enrichment
The API provides an enriched option to get additional cart details:
- Use `enriched=true` query parameter
- Returns additional fields like gross, coupon_code, and licenses

## Error Handling

Cart-related endpoints may return the following error responses:
- `400` - Bad Request
- `401` - Unauthorized
- `402` - Payment Required
- `404` - Cart Not Found

## Examples

### Get Cart Details Example

```bash
# Basic cart details
curl -X GET "https://api.freemius.com/v1/products/{product_id}/carts/{cart_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"

# Enriched cart details
curl -X GET "https://api.freemius.com/v1/products/{product_id}/carts/{cart_id}.json?enriched=true" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

### List Carts Example

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/carts.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

### Delete Cart Example

```bash
curl -X DELETE "https://api.freemius.com/v1/products/{product_id}/carts/{cart_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## Next Steps

After understanding carts, you can:
1. Learn about [Coupons](11-coupons.md)
2. Explore [Trials](12-trials.md)
3. Understand [Advanced Topics](14-advanced-topics.md)
