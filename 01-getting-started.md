# Getting Started with Freemius API

## Introduction

The Freemius API provides a comprehensive set of endpoints that allow you to interact with various aspects of the Freemius platform. This guide will help you get started with using the API effectively.

## API Overview

The Freemius API is a RESTful API that uses standard HTTP methods and returns responses in JSON format. The API enables you to:

- Manage products and their settings
- Handle license activations and verifications
- Process payments and subscriptions
- Manage users and installations
- Handle trials and coupons
- Track carts and checkouts

## Base URL

All API requests should be made to:

```
https://api.freemius.com/v1
```

## Authentication

The API uses Bearer authentication. You'll need to include your API key in the Authorization header of your requests:

```http
Authorization: Bearer YOUR_API_KEY
```

You can obtain your API key from the Freemius Developer Dashboard for your product or store.

## Request Format

The API accepts requests with JSON payloads and returns JSON responses. Always include the appropriate content-type header:

```http
Content-Type: application/json
```

## Response Format

All API responses are returned in JSON format. A typical successful response will contain the requested data, while error responses will include error details and messages.

### Success Response Example
```json
{
    "id": "12345",
    "type": "product",
    "attributes": {
        // Response data
    }
}
```

### Error Response Example
```json
{
    "error": {
        "code": "400",
        "message": "Invalid request parameters"
    }
}
```

## Rate Limiting

The API implements rate limiting to ensure fair usage. Be sure to handle rate limiting responses appropriately in your applications.

## Next Steps

Now that you understand the basics, you can:

1. Set up [Authentication](./02-authentication.md) for your requests
2. Learn about [Core Concepts](./03-core-concepts.md)
3. Start working with [Products](./04-products.md)

## Quick Start Example

Here's a simple example of making an API request to get product details:

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json"
```

Replace `{product_id}` with your actual product ID and `YOUR_API_KEY` with your API key.
