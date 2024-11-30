# Common Integration Scenario

This document provides an example of a common integration scenario using the Freemius API.

## Integration Overview

In this scenario, we will integrate a product with a third-party service to manage subscriptions and payments.

## Step 1: Create a Subscription

Example of creating a subscription for a product:

```bash
curl -X POST "https://api.freemius.com/v1/products/{product_id}/subscriptions.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
           "plan_id": "PLAN_ID_HERE",
           "user_id": "USER_ID_HERE",
           "payment_method": "credit_card"
         }'
```

## Step 2: Handle Payment Notifications

Example of handling payment notifications from the third-party service:

```bash
curl -X POST "https://api.freemius.com/v1/products/{product_id}/payments.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
           "amount": "10.00",
           "currency": "USD",
           "user_id": "USER_ID_HERE",
           "subscription_id": "SUBSCRIPTION_ID_HERE"
         }'
```

## Step 3: Update Subscription Status

Example of updating the subscription status based on payment success:

```bash
curl -X PUT "https://api.freemius.com/v1/products/{product_id}/subscriptions/{subscription_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
           "status": "active"
         }'
```

Replace `{product_id}`, `{user_id}`, `{subscription_id}`, `PLAN_ID_HERE`, and `YOUR_API_KEY` with the actual product ID, user ID, subscription ID, plan ID, and your API key in the examples above.
