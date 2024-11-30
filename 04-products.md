# Products

## Overview

Products in the Freemius API represent software that is being sold on the platform. This documentation is based on the API specification's Product schema and endpoints.

## Product Properties

According to the API specification, a product has the following key properties:

### Basic Information
- `id` - Unique identifier
- `secret_key` - Authorization key for the product
- `type` - Product type identifier

### Metrics
- `total_installs` - Total number of installations
- `active_installs` - Number of active installations
- `total_paid_installs` - Total number of paid installations
- `total_free_downloads` - Total number of free downloads
- `total_failed_purchases` - Number of failed payment transactions
- `earnings` - Product earnings information

## API Endpoints

### Get Product Details

```http
GET /products/{product_id}.json
```

Retrieves detailed information about a specific product.

#### Parameters
- `product_id` (path) - The ID of the product

#### Response
Returns the product object with all its properties.

### Product Ping

```http
GET /products/{product_id}/ping.json
```

Used to verify product connectivity and status.

### Product Settings

```http
GET /products/{product_id}/settings/{setting_id}.json
```

Retrieve product-specific settings.

#### Parameters
- `product_id` (path) - The ID of the product
- `setting_id` (path) - The ID of the setting to retrieve

## Product Management

### Product Plans
Products can have multiple plans that define feature availability and pricing. Access plan information through:

```http
GET /products/{product_id}/installs/{install_id}/plans.json
```

### Product Updates
Track and manage product updates through:

```http
GET /products/{product_id}/installs/{install_id}/updates.json
```

Get the latest update information:

```http
GET /products/{product_id}/installs/{install_id}/updates/latest.json
```

## Error Handling

Products endpoints may return the following error responses:
- `400` - Bad Request
- `401` - Unauthorized
- `402` - Payment Required
- `404` - Product Not Found

## Examples

### Get Product Details Example

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

### Check Product Status Example

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/ping.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## Next Steps

After understanding products, you can:
1. Learn about [Licensing](05-licensing.md)
2. Explore [Installations](06-installations.md)
3. Manage [Users](07-users.md)
