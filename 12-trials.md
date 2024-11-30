# Trials

## Overview

According to the API specification, a trial represents a user's trial period for a product. Trials are managed through specific endpoints and can be associated with product plans.

## Trial Properties

Based on the API specification's Trial schema:

### Basic Information
- `id` - Unique identifier
- Trial period details
- Associated plan and user information

## API Endpoints

### List Trials

```http
GET /products/{product_id}/trials.json
```

Retrieves a list of trials associated with a product.

#### Parameters
- `product_id` (path) - The ID of the product

### Start Trial

```http
POST /products/{product_id}/installs/{install_id}/plans/{plan_id}/trials.json
```

Initiates a trial for a specific plan and installation.

#### Parameters
- `product_id` (path) - The ID of the product
- `install_id` (path) - The ID of the installation
- `plan_id` (path) - The ID of the plan

## Trial Management

### Trial Initiation
The API provides functionality to:
- Start new trials
- Associate trials with specific plans
- Link trials to installations

### Trial Tracking
Trials can be:
- Listed and monitored
- Associated with specific installations
- Tracked for conversion

## Error Handling

Trial-related endpoints may return the following error responses:
- `400` - Bad Request
- `401` - Unauthorized
- `402` - Payment Required
- `404` - Trial Not Found

## Examples

### List Trials Example

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/trials.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

### Start Trial Example

```bash
curl -X POST "https://api.freemius.com/v1/products/{product_id}/installs/{install_id}/plans/{plan_id}/trials.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json"
```

## Next Steps

After understanding trials, you can:
1. Learn about [Webhooks](13-webhooks.md)
2. Explore [Advanced Topics](14-advanced-topics.md)
3. Review [Core Concepts](03-core-concepts.md)
