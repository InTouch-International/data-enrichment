# InTouch Services Library

InTouch Services Library is a collection of API endpoints encapsulated in a Postman collection, designed to interact with various individual data enrichment services.

## Table of Contents

- [Authorisation](#authorization)
- [API Endpoints](#api-endpoints)
    - [Address List](#address-list)
    - [Email Address List)](#email-address-list)
    - [Telephone List)](#telephone-list)
    - [People List](#people-list)
- [Setup](#setup)
- [Usage](#usage)
- [Environment Configuration](#environment-configuration)
- [Testing](#testing)

## Authorisation

Each call within the InTouch Services Library requires authorisation using a bearer token. The authorisation is achieved by making a call to the `Get Authorisation Token` endpoint with the client ID and secret, which in turn returns a unique bearer token that is saved at the Environment level for subsequent requests.

## API Endpoints

### Address List

This endpoint returns list of addresses for an individual with a given ID Number.

### Email Address List

Returns list of email records for an individual with a given ID Number or Email Address.

### Telephone List

This endpoint returns list of telephone numbers for an individual with a given ID Number.

### People List

Returns a list of people linked to the given ID Number.

## Setup

1. Clone the repository to your local machine.
2. Import the Postman collection into your Postman application.
3. Setup your environment variables for `{{base_url}}`, `{{auth_url}}`, `{{client_id}}`, and `{{client_secret}}`.

## Usage

1. Make a POST request to the `Get Authorisation Token` endpoint to retrieve the bearer token.
2. Use the bearer token to authorise the other endpoints within the collection.

## Environment Configuration

The repository includes an environment configuration file named `isl-dev.postman_environment.json`. This file contains predefined environment variables to facilitate testing and development in different stages. Here's how you can use it:

### Importing Environment Configuration

1. Download the `isl-dev.postman_environment.json` file from the repository.
2. Open Postman, click on the gear icon in the top right corner to manage environments.
3. Click the Import button and select the `isl-dev.postman_environment.json` file to import the environment configuration.

### Utilising Environment Variables

The `isl-dev.postman_environment.json` file defines the following environment variables:

- `base_url`: The base URL for the API endpoints.
- `admin_url`: The URL for admin access.
- `auth_url`: The URL for authorisation requests.
- `token`: The bearer token for authorisation. This will be populated after making a successful authorisation request.
- `client_id`: Your client ID for the authorisation request.
- `client_secret`: Your client secret for the authorisation request.

These variables allow for easier configuration and usage of the Postman collection. Make sure to populate the `client_id` and `client_secret` variables with your credentials before making authorisation requests.

### Example Usage

Here's an example of how you'd use an environment variable in a request:

- URL: `{{base_url}}?id=2ca14077-9213-4043-a4dc-315d95e6b09b`

The `{{base_url}}` placeholder will be replaced with the actual value defined in the `isl-dev.postman_environment.json` file, making the request URL: `https://api.dev.intouch.io/library/api/v3?id=2ca14077-9213-4043-a4dc-315d95e6b09b`.


## Testing

Use the Postman's built-in runner to execute the collection and observe the responses.