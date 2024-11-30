# Installations

## Overview

Installations in the Freemius API represent instances of a product installed on a site. This documentation is based on the API specification's Install schema and related endpoints.

## Installation Properties

According to the API specification, an installation has the following key properties:

### Basic Information
- `id` - Unique identifier
- `secret_key` - Authorization key for the installation
- `user_id` - Associated user identifier
- `license_id` - Associated license identifier (if applicable)

### Version Information
- `version` - Current version of the installation
- `last_served_update_version` - Last product version update used on the site

## API Endpoints

### Get Installation Details

```http
GET /products/{product_id}/installs/{install_id}.json
```

Retrieves detailed information about a specific installation.

#### Parameters
- `product_id` (path) - The ID of the product
- `install_id` (path) - The ID of the installation

### Update Installation

```http
PUT /products/{product_id}/installs/{install_id}.json
```

Updates a product installation's details.

### List Installations

```http
GET /products/{product_id}/installs.json
```

Retrieves a list of installations for a product.

### Handle Installation Clones

```http
PUT /products/{product_id}/installs/{install_id}/clones/{clone_id}.json
```

Resolves clone installations (e.g., staging or local environments).

### Installation Updates

#### List Updates

```http
GET /products/{product_id}/installs/{install_id}/updates.json
```

Retrieves available updates for an installation.

#### Get Latest Update

```http
GET /products/{product_id}/installs/{install_id}/updates/latest.json
```

Retrieves the latest available update.

### Installation Plans

```http
GET /products/{product_id}/installs/{install_id}/plans.json
```

Lists available plans for an installation.

### Start Trial

```http
POST /products/{product_id}/installs/{install_id}/plans/{plan_id}/trials.json
```

Initiates a trial for a specific plan.

## Installation Management

### Clone Handling
The API provides specific functionality for managing installation clones through the clone resolution endpoint.

### Update Management
Installations can track and manage updates through dedicated update endpoints.

## Error Handling

Installation endpoints may return the following error responses:
- `400` - Bad Request
- `401` - Unauthorized
- `402` - Payment Required
- `404` - Installation Not Found

## Examples

### Get Installation Example

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/installs/{install_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

### Update Installation Example

```bash
curl -X PUT "https://api.freemius.com/v1/products/{product_id}/installs/{install_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json"
```

### Check Updates Example

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/installs/{install_id}/updates/latest.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## Next Steps

After understanding installations, you can:
1. Learn about [Users](07-users.md)
2. Explore [Payments](08-payments.md)
3. Understand [Trials](12-trials.md)
