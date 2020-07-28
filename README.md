# Plaid Postman Collections
Welcome to the Postman Collections Quickstart Guide! If you're looking for a quick and easy way to get started with the Plaid API with no additional code, this is the place for you. [Postman](https://www.getpostman.com/product/api-client) is a great tool that allows users explore API functionality by manually sending API requests and receiving responses. We have created a collection of pre-populated HTTP requests that can be sent to the Plaid API. This quickstart is a step-by-step guide that will get you up and running with Postman and the Plaid’s Postman [collection](https://learning.postman.com/docs/postman/collections/intro-to-collections/) to enable you for ad-hoc exploration and testing.

If you are looking for a more in-depth guide and reference for the Plaid API, please refer to the [Plaid API documentation](https://plaid.com/docs/api).

![plaid-postman-overview](/images/plaid-postman-overview.png)

## Getting started
Follow these steps to quickly get started with the [Plaid API](https://plaid.com/docs):

1. [Sign up](https://dashboard.plaid.com/signup) with Plaid to get a set of API keys that are required for interacting with the API. [Here](https://plaid.com/docs/quickstart/#api-keys) is some documentation explaining what these keys are.
2. Download and install the [Postman app](https://www.getpostman.com/downloads/)
3. Install the Plaid Postman Collection. Click the "Run with Postman" button below to install the Plaid collection!
  [![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/bda53eac01b819772dd8#?env%5BSandbox%5D=W3sia2V5IjoiY2xpZW50X2lkIiwidmFsdWUiOiJZT1VSX0NMSUVOVF9JRCIsImVuYWJsZWQiOnRydWV9LHsia2V5Ijoic2VjcmV0X2tleSIsInZhbHVlIjoiWU9VUl9TRUNSRVRfS0VZIiwiZW5hYmxlZCI6dHJ1ZX0seyJrZXkiOiJwdWJsaWNfdG9rZW4iLCJ2YWx1ZSI6IiIsImVuYWJsZWQiOnRydWV9LHsia2V5IjoiYWNjZXNzX3Rva2VuIiwidmFsdWUiOiIiLCJlbmFibGVkIjp0cnVlfSx7ImtleSI6ImFzc2V0X3JlcG9ydF90b2tlbiIsInZhbHVlIjoiIiwiZW5hYmxlZCI6dHJ1ZX0seyJrZXkiOiJlbnZfdXJsIiwidmFsdWUiOiJzYW5kYm94LnBsYWlkLmNvbSIsImVuYWJsZWQiOnRydWV9LHsia2V5IjoiYWNjb3VudF9pZCIsInZhbHVlIjoiIiwiZW5hYmxlZCI6dHJ1ZX1d)
4. Once both the collection and the environment variables are imported into Postman, see the [Configuration](https://github.com/plaid/plaid-postman#configuration) section on how to correctly configure API keys with the collection.

### Configuration
The Plaid Postman collection uses [Postman environment variables](https://learning.getpostman.com/docs/postman/environments_and_globals/intro_to_environments_and_globals/) to simplify each API request. More information on managing Postman environments can be found at [Setting up an environment with variables](https://learning.getpostman.com/docs/postman/environments_and_globals/manage_environments/).

![plaid-postman-configuration](/images/plaid-postman-configuration.png)

1. Select the `Sandbox Public` environment in the top right corner
2. Click the `eye` icon to open the environment settings
3. Copy in your [Plaid API keys from your Plaid Dashboard](https://dashboard.plaid.com/account/keys), into each field:
  - `client_id`
  - `secret`
4. Save your changes and start making Plaid API requests!

## Collection endpoints
The following collection is a fully-featured set of pre-filled requests that allow you to test the [Plaid API](https://plaid.com/docs), and visualize the responses in a friendly format.

* **Link Tokens**
  * **Create Link Token** - Creates a `link_token` for the default Link flow.
  * **Create Link Token - Update Mode ** - Creates a `link_token` for the update mode Link flow.
  * **Create Link Token - Payment Initiation ** - Creates a `link_token` for the payment initiation Link flow.
  * **Create Link Token - OAuth ** - Creates a `link_token` for the OAuth Link flow.

* **Items**
  * **Create Item [Sandbox Only]** - Creates an Item by generating a public token. This endpoint only works in the Sandbox environment. Items can only be created through Plaid Link in the development and production environments.
  * **Exchange Token** - Exchanges a public token for an access token.
  * **Retrieve Item** - Retrieves information about an Item.
  * **Retrieve an Item's Accounts** - Retrieves all available accounts for an Item.
  * **Create a `public_token`** - Generates a `public_token` for an existing Item for use in Plaid Link's [update mode](https://plaid.com/docs/#updating-items-via-link).
  * **Rotate Access Token** - Returns a new access token and invalidates the old one.
  * **Update an Item's Webhook** - Updates an Item's webhook url.
  * **Simulate ITEM_LOGIN_REQUIRED [Sandbox Only]** - Sets an Item in an ITEM_LOGIN_REQUIRED state. Check our [Errors](https://plaid.com/docs/#errors-overview) section in our docs for more information.
  * **Remove Item** - Deletes an Item using its access token.

* **Auth**
  * **Retrieve Auth** - Retrieves the bank account and routing numbers associated with an Item’s checking and savings accounts, along with high-level account data and balances.

* **Transactions**
  * **Retrieve Transactions** - Retrieves user-authorized transaction data for credit and depository-type Accounts. Transaction data is standardized across financial institutions, and in many cases transactions are linked to a clean name, entity type, location, and category. Similarly, account data is standardized and returned with a clean name, number, balance, and other meta information where available.

* **Balance**
  * **Retrieve Balance** - Retrieves the real-time balance for each of an Item’s accounts.

* **Identity**
  * **Retrieve Identity** -  Retrieves various account holder information on file with the financial institution, including names, emails, phone numbers, and addresses.

* **Income**
  * **Retrieve Income** - Retrieves information pertaining to an Item’s income. In addition to the annual income, detailed information will be provided for each contributing income stream (or job).

* **Liabilities**
  * **Retrieve Liabilities** - Retrieves information pertaining to an Item's liabilities.

* **Investments**
  * **Retrieve Investments Holdings** - Retrieves information pertaining to an Item's Holdings for the Investments product.
  * **Retrieve Investments Transactions** - Retrieves information pertaining to an Item's Transactions for the Investments product.

* **Assets**
  * **Create Asset Report** - Creates an Asset Report.
  * **Retrieve an Asset Report (JSON)** - Retrieves an Asset Report in JSON.
  * **Retrieve an Asset Report (PDF)** - Retrieves an Asset Report in PDF.
  * **Create Audit Copy** - Plaid can provide an Audit Copy of any Asset Report directly to a participating third party on your behalf. This endpoint creates that Audit Copy.
  * **Remove Asset Report** - Removes an Asset Report.
  * **Remove Audit Copy** - Removes an Audit Copy.
  * **Refresh Asset Report** - Create a new Asset Report based on the old one, but with the most recent data available from the financial institution(s).

* **Institutions**
  * **Search Institution by Name** - Retrieves information about a specific institution by name.
  * **Search Institution by ID** - Retrieves information about a specific institution by ID.
  * **Retrieve Institution List** - Retrieves a list of all supported institutions.

* **Categories**
  * **Retrieve Categories** - Retrieves detailed information on categories returned by Plaid. This endpoint does not require authentication.

## Useful Tools
[Webhook Tester](https://webhook.site/) is a great tool for receiving webhook calls. Generate a webhook url on this site and use that url for any Postman requests that require you to specify a webhook url. You can go on Webhook Tester to see a list of all requests being made to that url.


## Important Note
The `/public_token/create` endpoint is only available in the `sandbox` environment. It exists only for testing purposes and simulates an Item Creation via the Plaid Link module. Items cannot be created directly via an endpoint for the `development` and `production` environments and can only be created through Plaid Link.
