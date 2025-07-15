# setup-testing-keycloak.sh

This script sets up a local [Keycloak](https://www.keycloak.org/) instance for development and testing in the context of the [GlobaLeaks](https://www.globaleaks.org/) project.

It automates the provisioning of a Keycloak realm, test user, and client required to test GlobaLeaks' OpenID Connect (OIDC) integration locally, using Docker.

## What It Does

- Pulls the latest Keycloak Docker image from [quay.io](https://quay.io/)
- Starts a local Keycloak container on port `9090`
- Waits for Keycloak to become available
- Automatically:
  - Creates a new realm named `globaleaks`
  - Adds a user `globaleaks` with password `globaleaks`
  - Configures a client `globaleaks` with direct access grants and `https://127.0.0.1:8443/*` as a redirect URI

> This setup is designed specifically to test OIDC authentication in GlobaLeaks without relying on an external identity provider.

## Prerequisites

- Docker
- curl

## Usage

```bash
chmod +x setup-testing-keycloak.sh
./setup-testing-keycloak.sh
