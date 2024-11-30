# Coupons

## Overview

According to the API specification, a coupon can be used during the checkout to apply discounts. Coupons are managed through dedicated endpoints for creation and listing.

## Coupon Properties

Based on the API specification's Coupon schema:

### Basic Information
- `id` - Unique identifier
- Discount information
- Usage and validity details

## API Endpoints

### List Coupons

```http
GET /products/{product_id}/coupons.json
```

Retrieves a list of coupons associated with a product.

#### Parameters
- `product_id` (path) - The ID of the product

### Create Coupon

```http
POST /products/{product_id}/coupons.json
```

Creates a new coupon for a product.

#### Parameters
- `product_id` (path) - The ID of the product

## Coupon Management

### Coupon Creation
The API allows creating new coupons with specific:
- Discount values
- Usage limitations
- Validity periods

### Coupon Usage
Coupons can be:
- Applied during checkout
- Used with carts
- Tracked for usage statistics

## Error Handling

Coupon-related endpoints may return the following error responses:
- `400` - Bad Request
- `401` - Unauthorized
- `402` - Payment Required
- `404` - Coupon Not Found

## Examples

### List Coupons Example

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/coupons.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

### Create Coupon Example

```bash
curl -X POST "https://api.freemius.com/v1/products/{product_id}/coupons.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json"
```

## Next Steps

After understanding coupons, you can:
1. Learn about [Trials](12-trials.md)
2. Explore [Webhooks](13-webhooks.md)
3. Understand [Advanced Topics](14-advanced-topics.md)
