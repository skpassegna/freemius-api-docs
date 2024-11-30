# Core Concepts

This chapter covers the fundamental concepts and entities in the Freemius API, based on the API specification.

## Products

A product represents software that is being sold on Freemius. According to the API specification, products have the following characteristics:

### Product Properties
- Unique identifier
- Secret key for authorization
- Various metrics including:
  - Total installations
  - Active installations
  - Total earnings
  - Failed purchases

## Licensing System

The API handles licenses which represent authorization to use available features of a product.

### License Types and Management
- Licenses are tied to specific products
- Can be activated and deactivated
- May be associated with subscriptions

## Users

Users in the Freemius system are individuals who are registered through product usage.

### User Characteristics
- Can own product licenses
- May be linked to free versions of products
- Have associated installations and payments

## Installations

Installations represent instances of a product installed on a site.

### Installation Types
- May or may not have an associated license
- Can be cloned (e.g., staging or local environments)
- Track update versions and status

## Subscriptions

Subscriptions are created when users purchase or subscribe to a product plan.

### Subscription Features
- Associated with specific plans
- Track renewal and payment status
- Handle trial periods

## Trials

The trial system allows users to test products before purchase.

### Trial Characteristics
- Time-limited access to product features
- Can be started for specific plans
- Track usage and conversion

## Payments

The payment system handles all financial transactions.

### Payment Types
- Initial subscription payments
- Renewal payments
- One-time payments
- Refunds and disputes

## Carts

Carts represent a buyer's intent to purchase a product.

### Cart Features
- Track purchase intentions
- Handle checkout process
- Support coupon applications

## Plans

Plans define the features available to users.

### Plan Characteristics
- Different pricing options
- Various billing cycles
- Feature sets and quotas

## Next Steps

Now that you understand the core concepts, you can explore specific areas in detail:
1. [Products](./04-products.md)
2. [Licensing](./05-licensing.md)
3. [Installations](./06-installations.md)
