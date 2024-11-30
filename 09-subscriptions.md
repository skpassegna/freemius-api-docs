# Subscriptions

## Overview

According to the API specification, a subscription is created when a user uses Freemius Checkout to purchase or subscribe to a plan of a product.

## Subscription Properties

Based on the API specification's Subscription schema:

### Basic Information
- `id` - Unique identifier
- Associated plan and user information
- Subscription status and details

## API Endpoints

### Get Subscription Details

```http
GET /products/{product_id}/subscriptions/{subscription_id}.json
```

Retrieves detailed information about a specific subscription.

#### Parameters
- `product_id` (path) - The ID of the product
- `subscription_id` (path) - The ID of the subscription

### List Subscriptions

```http
GET /products/{product_id}/subscriptions.json
```

Retrieves a list of subscriptions associated with a product.

### List User Subscriptions

```http
GET /products/{product_id}/users/{user_id}/subscriptions.json
```

Retrieves subscriptions associated with a specific user.

### List License Subscriptions

```http
GET /products/{product_id}/installs/{install_id}/licenses/{license_id}/subscriptions.json
```

Retrieves subscriptions associated with a specific license.

## Subscription Management

### Subscription Types
The API handles subscriptions for:
- Product plans
- Different billing cycles
- Various feature sets

### Subscription States
Subscriptions can have different states and properties tracking:
- Active status
- Renewal information
- Payment status

## Error Handling

Subscription-related endpoints may return the following error responses:
- `400` - Bad Request
- `401` - Unauthorized
- `402` - Payment Required
- `404` - Subscription Not Found

## Examples

### Get Subscription Details Example

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/subscriptions/{subscription_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

### List Product Subscriptions Example

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/subscriptions.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

### List User Subscriptions Example

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/users/{user_id}/subscriptions.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## Next Steps

After understanding subscriptions, you can:
1. Learn about [Carts](10-carts.md)
2. Explore [Coupons](11-coupons.md)
3. Understand [Trials](12-trials.md)
