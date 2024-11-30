# Common Use Cases

This document provides examples of common use cases for the Freemius API.

## User Registration and Activation

Example of registering a new user and activating their account:

```bash
curl -X POST "https://api.freemius.com/v1/products/{product_id}/users.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
           "email": "user@example.com",
           "first_name": "John",
           "last_name": "Doe"
         }'

# Activate user
curl -X POST "https://api.freemius.com/v1/products/{product_id}/users/{user_id}/activate.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## Subscription Renewal

Example of renewing a subscription:

```bash
curl -X POST "https://api.freemius.com/v1/products/{product_id}/subscriptions/{subscription_id}/renew.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## License Key Generation

Example of generating a new license key for a product:

```bash
curl -X POST "https://api.freemius.com/v1/products/{product_id}/licenses.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
           "plan_id": "PLAN_ID_HERE",
           "user_id": "USER_ID_HERE"
         }'
```

Replace `{product_id}`, `{user_id}`, `{subscription_id}`, `PLAN_ID_HERE`, and `YOUR_API_KEY` with the actual product ID, user ID, subscription ID, plan ID, and your API key in the examples above.
