# Users

## Overview

According to the API specification, a User is a person who is registered to Freemius through usage of one or more products. Users can own licenses or be linked to free versions of products.

## User Properties

Based on the API specification's User schema:

### Basic Information
- `id` - Unique identifier
- Properties related to user identification and status
- Associated product relationships

## API Endpoints

### List Users

```http
GET /products/{product_id}/users.json
```

Retrieves a list of users associated with a product.

#### Parameters
- `product_id` (path) - The ID of the product

### Create User

```http
POST /products/{product_id}/users.json
```

Creates a new user for a product.

### List User Installations

```http
GET /products/{product_id}/users/{user_id}/installs.json
```

Retrieves installations associated with a specific user.

#### Parameters
- `product_id` (path) - The ID of the product
- `user_id` (path) - The ID of the user

### List User Payments

```http
GET /products/{product_id}/users/{user_id}/payments.json
```

Retrieves payments made by a specific user.

### List User Subscriptions

```http
GET /products/{product_id}/users/{user_id}/subscriptions.json
```

Retrieves subscriptions associated with a specific user.

## User Management

### User Creation
The API allows creating new users through the POST endpoint with appropriate user data.

### User Relationships
Users can be associated with:
- Product installations
- Payments
- Subscriptions

## Error Handling

User-related endpoints may return the following error responses:
- `400` - Bad Request
- `401` - Unauthorized
- `402` - Payment Required
- `404` - User Not Found

## Examples

### List Users Example

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/users.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

### Create User Example

```bash
curl -X POST "https://api.freemius.com/v1/products/{product_id}/users.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json"
```

### Get User Installations Example

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/users/{user_id}/installs.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## Next Steps

After understanding user management, you can:
1. Learn about [Payments](08-payments.md)
2. Explore [Subscriptions](09-subscriptions.md)
3. Understand [Trials](12-trials.md)
