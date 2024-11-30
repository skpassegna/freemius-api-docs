# Installation Tracking Workflow

This document provides an example workflow for tracking installations using the Freemius API.

## Retrieve Installation Details

Example of retrieving details of a specific installation:

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/installs/{install_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## Update Installation

Example of updating installation information:

```bash
curl -X PUT "https://api.freemius.com/v1/products/{product_id}/installs/{install_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY" \
     -H "Content-Type: application/json" \
     -d '{
           "version": "NEW_VERSION_HERE"
         }'
```

## List Installations

Example of listing all installations associated with a product:

```bash
curl -X GET "https://api.freemius.com/v1/products/{product_id}/installs.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

## Handle Installation Clones

Example of handling installation clones:

```bash
curl -X PUT "https://api.freemius.com/v1/products/{product_id}/installs/{install_id}/clones/{clone_id}.json" \
     -H "Authorization: Bearer YOUR_API_KEY"
```

Replace `{product_id}`, `{install_id}`, `{clone_id}`, `NEW_VERSION_HERE`, and `YOUR_API_KEY` with the actual product ID, installation ID, clone ID, new version, and your API key in the examples above.
