# Licensing

## Overview

The licensing system in the Freemius API handles license management, activation, and verification. This documentation is based on the API specification's License schema and endpoints.

## License Properties

According to the API specification, a license has the following characteristics:

### Basic Properties
- `id` - Unique identifier for the license
- `user_id` - Associated user identifier
- `plan_id` - Associated plan identifier

### License States
The license can be in various states and includes:
- Activation status
- Installation tracking
- Usage limitations

## API Endpoints

### License Activation

```http
POST /products/{product_id}/licenses/activate.json
```

Activates a license for a product.

#### Parameters
- `product_id` (path) - The ID of the product

### License Deactivation

```http
POST /products/{product_id}/licenses/deactivate.json
```

Deactivates a license for a product.

#### Parameters
- `product_id` (path) - The ID of the product

### List Licenses

```http
GET /products/{product_id}/licenses.json
```

Retrieves a list of licenses associated with a product.

### Get Active License by ID

```http
GET /products/{product_id}/installs/{install_id}/licenses/{license_id}.json
```

Retrieves details of a specific active license.

#### Parameters
- `product_id` (path) - The ID of the product
- `install_id` (path) - The ID of the installation
- `license_id` (path) - The ID of the license

### List License Subscriptions

```http
GET /products/{product_id}/installs/{install_id}/licenses/{license_id}/subscriptions.json
```

Retrieves subscriptions associated with a specific license.

## License Management

### License Verification
The API provides endpoints to verify license validity and status through the activation and deactivation endpoints.

### Installation Association
Licenses are associated with specific installations and can be tracked through the installation endpoints.

## Error Handling

License-related endpoints may return the following error responses:
- `400` - Bad Request (e.g., invalid license data)
- `401` - Unauthorized
- `402` - Payment Required
- `404` - License Not Found

## Examples

### Activate License Example

```bash
curl -X POST "https://api.freemius.com/v1/products/{product_id}/licenses/activate.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json"
```

### Deactivate License Example

```bash
curl -X POST "https://api.freemius.com/v1/products/{product_id}/licenses/deactivate.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json"
```

### Get License Details Example

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/installs/{install_id}/licenses/{license_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## Next Steps

After understanding licensing, you can:
1. Learn about [Installations](06-installations.md)
2. Explore [Users](07-users.md)
3. Understand [Subscriptions](09-subscriptions.md)
