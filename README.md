# Canada Post API Insomnia Collections

![REST](https://img.shields.io/badge/API-REST-blue)
![OAuth2](https://img.shields.io/badge/Auth-OAuth_2.0-green)
![Insomnia](https://img.shields.io/badge/Tested-Insomnia-6f42c1)
![YAML](https://img.shields.io/badge/Format-YAML-orange)

## Overview

This repository contains a comprehensive set of **Insomnia API
Collections** for the Canada Post Developer Platform. The collections
are intended to help developers, integration partners, solution
providers, and testers quickly import, configure, and execute API
requests for both **Merchant** and **Platform** scenarios.

The requests are organized into logical functional areas to simplify
onboarding, API exploration, troubleshooting, regression testing, and
integration validation.

------------------------------------------------------------------------

# Repository Contents

``` text
.
├── Merchant/
│   ├── API Authentication
│   ├── Service Information
│   ├── Rating
│   ├── Shipping
│   ├── Tracking
│   ├── PickUp
│   ├── Return
│   ├── Customer Information
│   ├── Post Office
│   └── Complete Merchant Collection
│
├── Platform/
│   ├── API Authentication
│   ├── Service Information
│   ├── Rating
│   ├── Shipping
│   ├── Tracking
│   ├── PickUp
│   ├── Return
│   ├── Customer Information
│   ├── Post Office
│   └── Complete Platform Collection
│
└── README.md
```

------------------------------------------------------------------------

# Features

-   Ready-to-import Insomnia collections
-   REST API examples
-   OAuth 2.0 authentication workflow
-   Organized by functional area
-   Supports development, QA, UAT, and production environments
-   Ideal for manual testing and regression testing
-   Easily extended with new requests and endpoints

------------------------------------------------------------------------

# Prerequisites

-   Insomnia (latest version recommended)
-   Valid Canada Post Developer credentials
-   Appropriate API access and permissions
-   Network connectivity to the target environment

------------------------------------------------------------------------

# Importing into Insomnia

1.  Open Insomnia.
2.  Select **Import**.
3.  Choose **From File**.
4.  Select the desired collection.
5.  Configure environment variables.
6.  Authenticate using OAuth 2.0 (where applicable).
7.  Execute requests.

------------------------------------------------------------------------

# Collections

## Merchant Collection

Designed for merchants integrating directly with Canada Post APIs.

Functional areas include:

-   API Authentication
-   Service Information
-   Rating
-   Shipping
-   Tracking
-   PickUp
-   Returns
-   Customer Information
-   Post Office
-   Complete Merchant Collection

------------------------------------------------------------------------

## Platform Collection

Designed for shipping platforms, marketplaces, and technology partners
integrating on behalf of multiple merchants.

Functional areas include:

-   API Authentication
-   Service Information
-   Rating
-   Shipping
-   Tracking
-   PickUp
-   Returns
-   Customer Information
-   Post Office
-   Complete Platform Collection

------------------------------------------------------------------------

# Authentication

The collections use OAuth 2.0 where required.

Typical workflow:

1.  Obtain an access token.
2.  Store the token in the active environment.
3.  Execute API requests using the Bearer token.
4.  Refresh expired tokens when necessary.

------------------------------------------------------------------------

# Environment Configuration

It is recommended to create separate environments for:

-   Development
-   QA
-   Staging
-   Production

Typical environment variables include:

  Variable        Description
  --------------- ----------------------------------
  Base URL        Target API host
  Client ID       OAuth client identifier
  Client Secret   OAuth client secret
  Access Token    Bearer token
  Username        User credentials (if applicable)
  Password        User credentials (if applicable)

> Never commit credentials or production secrets to source control.

------------------------------------------------------------------------

# Recommended Testing

These collections support:

-   Smoke Testing
-   Functional Testing
-   Regression Testing
-   Integration Testing
-   User Acceptance Testing
-   Negative Testing
-   API Validation

------------------------------------------------------------------------

# Best Practices

-   Use environment variables instead of hardcoded values.
-   Validate request payloads before execution.
-   Verify HTTP status codes and response bodies.
-   Keep collections synchronized with API changes.
-   Version collections whenever new APIs or breaking changes are
    introduced.

------------------------------------------------------------------------

# Troubleshooting

## HTTP 400 -- Bad Request

-   Verify required fields.
-   Validate request payload.
-   Check parameter formatting.

## HTTP 401 -- Unauthorized

-   Verify OAuth credentials.
-   Ensure the access token has not expired.

## HTTP 403 -- Forbidden

-   Confirm API permissions.
-   Verify account authorization.

## HTTP 500 -- Server Error

-   Retry the request.
-   Verify the target environment.
-   Contact API support if the issue persists.

------------------------------------------------------------------------

# Contributing

Contributions are welcome.

When updating the collections:

1.  Maintain the existing folder structure.
2.  Use meaningful request names.
3.  Test modified requests before committing.
4.  Update documentation where appropriate.

------------------------------------------------------------------------

# Versioning

Follow semantic versioning whenever possible.

Example:

-   v1.0.0 -- Initial release
-   v1.1.0 -- New APIs added
-   v1.2.0 -- Enhancements
-   v2.0.0 -- Breaking changes

------------------------------------------------------------------------

# License

Unless otherwise specified, this repository is intended for use with
Canada Post API integrations. Refer to your organization's policies
before redistributing or modifying the collections.

------------------------------------------------------------------------

# Acknowledgements

These collections were created to provide developers with a consistent,
reusable, and maintainable set of Insomnia requests for Canada Post API
integration, testing, and troubleshooting.
