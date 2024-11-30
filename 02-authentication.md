# Authentication

## Overview

The Freemius API uses Bearer authentication to secure API requests. This chapter details the authentication process and security best practices.

## Authentication Methods

### Bearer Authentication

The API uses the standard Bearer authentication scheme. You need to include your API key in the Authorization header of your requests:

```http
Authorization: Bearer YOUR_API_KEY
```

According to the API specification, you can obtain the API Key from the Freemius Developer Dashboard for a product or a store.

## Security Schemes

The API defines the following security scheme:

```yaml
type: http
scheme: bearer
```

## Making Authenticated Requests

### Request Format

All authenticated requests must include:
1. The Authorization header with your Bearer token
2. Proper Content-Type header (application/json)

Example of an authenticated request:

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json"
```

### Authentication Errors

Common authentication-related HTTP status codes:

- `401 Unauthorized`: Invalid or missing authentication credentials
- `403 Forbidden`: Valid authentication but insufficient permissions

## Best Practices

1. **Secure Storage**
   - Never expose your API key in client-side code
   - Store API keys securely in environment variables or secure configuration files

2. **Key Management**
   - Use different API keys for different environments (development, production)
   - Regularly rotate API keys for security

3. **Error Handling**
   - Implement proper error handling for authentication failures
   - Log authentication errors appropriately without exposing sensitive details

## Next Steps

Once you've set up authentication, you can:
1. Learn about [Core Concepts](./03-core-concepts.md)
2. Start working with [Products](./04-products.md)
3. Explore [User Management](./07-users.md)
