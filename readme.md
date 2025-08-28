# Laravel Cashier - Braintree Edition

[![Build Status](https://travis-ci.org/laravel/cashier-braintree.svg)](https://travis-ci.org/laravel/cashier-braintree)
[![Total Downloads](https://poser.pugx.org/laravel/cashier-braintree/d/total.svg)](https://packagist.org/packages/laravel/cashier-braintree)
[![Latest Stable Version](https://poser.pugx.org/laravel/cashier-braintree/v/stable.svg)](https://packagist.org/packages/laravel/cashier-braintree)
[![Latest Unstable Version](https://poser.pugx.org/laravel/cashier-braintree/v/unstable.svg)](https://packagist.org/packages/laravel/cashier-braintree)
[![License](https://poser.pugx.org/laravel/cashier-braintree/license.svg)](https://packagist.org/packages/laravel/cashier-braintree)

## Introduction

Laravel Cashier Braintree provides an expressive, fluent interface to [Braintree's](https://www.braintreepayments.com/) subscription billing services. It handles almost all of the boilerplate subscription billing code you are dreading writing. In addition to basic subscription management, Cashier Braintree can handle coupons, swapping subscription, cancellation grace periods, and even generate invoice PDFs.

## Supports

Supports PHP ^7.2, Laravel ~6.12|~6.13|~6.14, and phpunit ~8.0

## Testing

You will need to set the following details locally and on your Braintree account in order to run the library's tests.

### Local

#### Environment Variables

    BRAINTREE_MERCHANT_ID=
    BRAINTREE_PUBLIC_KEY=
    BRAINTREE_PRIVATE_KEY=
    BRAINTREE_MODEL=Laravel\Cashier\Tests\User

You can set these variables in the `phpunit.xml.dist` file.

### Braintree

#### Plans

    * Plan ID: monthly-10-1, Price: $10, Billing cycle of every month
    * Plan ID: monthly-10-2, Price: $10, Billing cycle of every month
    * Plan ID: yearly-100-1, Price: $100, Billing cycle of every 12 months

#### Discount

    * Discount ID: coupon-1, Price: $5
    * Discount ID: plan-credit, Price $1

## Official Documentation

Documentation for Cashier Braintree can be found on the [Laravel website](https://laravel.com/docs/5.8/braintree).

## Publishing to Packagist

### Prerequisites

1. **Packagist Account**: Create an account at [packagist.org](https://packagist.org) if you don't have one
2. **Repository Access**: Ensure you have push access to this GitHub repository
3. **Composer**: Make sure you have Composer installed locally

### Initial Setup (First Time Only)

1. **Submit Package to Packagist**:

    - Log in to [packagist.org](https://packagist.org)
    - Click "Submit" in the navigation
    - Enter the GitHub repository URL: `https://github.com/ahadcove/cashier-braintree`
    - Click "Check" and then "Submit"

2. **Setup Auto-updating** (Recommended):
    - In Packagist, go to your package page
    - Click "Settings" → "Webhooks"
    - Copy the webhook URL
    - In GitHub, go to Settings → Webhooks → Add webhook
    - Paste the Packagist webhook URL
    - Set Content type to `application/json`
    - Select "Just the push event"
    - Save the webhook

### Publishing a New Version

1. **Update Version Dependencies** (if needed):

    ```bash
    # Update composer.json with new PHP or Laravel versions if required
    composer update
    ```

2. **Run Tests**:

    ```bash
    composer test
    # or
    vendor/bin/phpunit
    ```

3. **Commit Changes**:

    ```bash
    git add .
    git commit -m "feat: your feature description"
    git push origin 12.2
    ```

4. **Create and Push Tag**:

    ```bash
    # Semantic versioning: MAJOR.MINOR.PATCH
    git tag -a v12.2.0 -m "Release version 12.2.0"
    git push --tags
    ```

5. **Verify on Packagist**:
    - If webhooks are configured: Package will auto-update within minutes
    - Manual update: Go to your package on Packagist and click "Update"

### Version Naming Convention

Follow [Semantic Versioning](https://semver.org/):

-   **MAJOR** version: Incompatible API changes
-   **MINOR** version: Add functionality (backwards-compatible)
-   **PATCH** version: Bug fixes (backwards-compatible)

Example: `v12.2.1`

### Troubleshooting

-   **Package not updating**: Check webhook delivery in GitHub Settings → Webhooks
-   **Composer can't find package**: Run `composer clear-cache`
-   **Version constraints issues**: Ensure your `composer.json` version constraints are valid
