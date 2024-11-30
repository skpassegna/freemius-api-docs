# Trial to Paid Conversion Workflow

This document provides an example workflow for converting a trial to a paid subscription using the Freemius API.

## Start a Trial

Example of starting a trial for a specific plan:

```bash
curl -X POST "https://api.freemius.com/v1/products/{product_id}/installs/{install_id}/plans/{plan_id}/trials.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json"
```

## Monitor Trial Usage

Example of monitoring trial usage and status:

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/installs/{install_id}/trials.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## Convert Trial to Paid Subscription

Example of converting a trial to a paid subscription:

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

## Cancel Trial

Example of canceling a trial:

```bash
curl -X DELETE "https://api.freemius.com/v1/products/{product_id}/installs/{install_id}/trials/{trial_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

Replace `{product_id}`, `{install_id}`, `{plan_id}`, `{trial_id}`, `PLAN_ID_HERE`, `USER_ID_HERE`, and `YOUR_API_KEY` with the actual product ID, installation ID, plan ID, trial ID, plan ID, user ID, and your API key in the examples above.
