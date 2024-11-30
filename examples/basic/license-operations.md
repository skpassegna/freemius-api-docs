# License Operations Examples

This document provides examples of how to activate and verify licenses using the Freemius API.

## Activate a License

Example of activating a license for a product:

```bash
curl -X POST "https://api.freemius.com/v1/products/{product_id}/licenses/activate.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
           "license_key": "LICENSE_KEY_HERE"
         }'
```

## Deactivate a License

Example of deactivating a license for a product:

```bash
curl -X POST "https://api.freemius.com/v1/products/{product_id}/licenses/deactivate.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
           "license_key": "LICENSE_KEY_HERE"
         }'
```

## Verify a License

Example of verifying a license:

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/licenses/{license_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

Replace `{product_id}`, `{license_id}`, and `LICENSE_KEY_HERE` with the actual product ID, license ID, and license key, respectively, and `YOUR_API_KEY` with your API key in the examples above.
