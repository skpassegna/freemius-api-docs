# User Management Examples

This document provides examples of how to create and manage users using the Freemius API.

## Create a User

Example of creating a new user for a product:

```bash
curl -X POST "https://api.freemius.com/v1/products/{product_id}/users.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
           "email": "newuser@example.com",
           "first_name": "John",
           "last_name": "Doe"
         }'
```

## Retrieve User Details

Example of retrieving user details:

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/users/{user_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## Update User Information

Example of updating user information:

```bash
curl -X PUT "https://api.freemius.com/v1/products/{product_id}/users/{user_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
           "first_name": "Jane",
           "last_name": "Doe"
         }'
```

## Delete a User

Example of deleting a user:

```bash
curl -X DELETE "https://api.freemius.com/v1/products/{product_id}/users/{user_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

Replace `{product_id}`, `{user_id}`, and `YOUR_API_KEY` with the actual product ID, user ID, and your API key in the examples above.
