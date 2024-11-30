# Payments

## Overview

According to the API specification, payments in the Freemius API represent acknowledgments of payments received for various cases:
- Initial payment of a subscription
- Renewal payment of a subscription
- One-time payment for a product
- Refunds, disputes, and chargebacks

## Payment Properties

Based on the API specification's Payment schema:

### Basic Information
- `id` - Unique identifier
- `user_id` - Associated user identifier
- Payment details and status information

## API Endpoints

### Get Payment Details

```http
GET /products/{product_id}/payments/{payment_id}.json
```

Retrieves detailed information about a specific payment.

#### Parameters
- `product_id` (path) - The ID of the product
- `payment_id` (path) - The ID of the payment

### List Payments

```http
GET /products/{product_id}/payments.json
```

Retrieves a list of payments associated with a product.

### List Installation Payments

```http
GET /products/{product_id}/installs/{install_id}/payments.json
```

Retrieves payments associated with a specific installation.

#### Parameters
- `product_id` (path) - The ID of the product
- `install_id` (path) - The ID of the installation

### List User Payments

```http
GET /products/{product_id}/users/{user_id}/payments.json
```

Retrieves payments made by a specific user.

## Payment Management

### Payment Types
The API handles various types of payments:
- Subscription payments (initial and renewals)
- One-time payments
- Refunds and disputes

### Payment Tracking
Payments can be tracked at different levels:
- Product level
- Installation level
- User level

## Error Handling

Payment-related endpoints may return the following error responses:
- `400` - Bad Request
- `401` - Unauthorized
- `402` - Payment Required
- `404` - Payment Not Found

## Examples

### Get Payment Details Example

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/payments/{payment_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

### List Product Payments Example

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/payments.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

### List User Payments Example

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/users/{user_id}/payments.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## Next Steps

After understanding payments, you can:
1. Learn about [Subscriptions](09-subscriptions.md)
2. Explore [Carts](10-carts.md)
3. Understand [Coupons](11-coupons.md)
