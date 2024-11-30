# Subscription Workflow Examples

This document provides examples of managing the complete subscription lifecycle using the Freemius API.

## Create a Subscription

Example of creating a new subscription for a product:

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

## Retrieve Subscription Details

Example of retrieving subscription details:

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/subscriptions/{subscription_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## Update Subscription

Example of updating subscription information:

```bash
curl -X PUT "https://api.freemius.com/v1/products/{product_id}/subscriptions/{subscription_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
           "plan_id": "NEW_PLAN_ID_HERE"
         }'
```

## Cancel Subscription

Example of canceling a subscription:

```bash
curl -X DELETE "https://api.freemius.com/v1/products/{product_id}/subscriptions/{subscription_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

Replace `{product_id}`, `{subscription_id}`, `PLAN_ID_HERE`, `USER_ID_HERE`, and `YOUR_API_KEY` with the actual product ID, subscription ID, plan ID, user ID, and your API key in the examples above.
