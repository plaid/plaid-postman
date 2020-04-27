# Plaid Postman Collections
Welcome to the Postman Collections Quickstart Guide! If you're looking for a quick and easy way to get started with the Plaid API with no additional code, this is the place for you. [Postman](https://www.getpostman.com/product/api-client) is a great tool that allows users explore API functionality by manually sending API requests and receiving responses. We have created a collection of pre-populated HTTP requests that can be sent to the Plaid API. This quickstart is a step-by-step guide that will get you up and running with Postman and the Plaid’s Postman [collection](https://www.getpostman.com/docs/v6/postman/collections/intro_to_collections) to enable you for ad-hoc exploration and testing.

If you are looking for a more in-depth guide and reference for the Plaid API, please refer to the [Plaid API documentation](https://plaid.com/docs/api).

![plaid-postman-overview](/images/plaid-postman-overview.png)

## Getting started
Follow these steps to quickly get started with the [Plaid API](https://plaid.com/docs):

1. [Sign up](https://dashboard.plaid.com/signup) with Plaid to get a set of API keys that are required for interacting with the API. [Here](https://plaid.com/docs/quickstart/#api-keys) is some documentation explaining what these keys are.
2. Download and install the [Postman app](https://www.getpostman.com/downloads/)
3. Install the Plaid Postman Collection. Click the "Run with Postman" button below to install the Plaid collection!
  [![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/da0330da603762f03b95#?env%5BSandbox%20Public%5D=W3sia2V5IjoiY2xpZW50X2lkIiwidmFsdWUiOiIiLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoidGV4dCJ9LHsia2V5IjoicHVibGljX2tleSIsInZhbHVlIjoiIiwiZW5hYmxlZCI6dHJ1ZSwidHlwZSI6InRleHQifSx7ImtleSI6InNlY3JldF9rZXkiLCJ2YWx1ZSI6IiIsImVuYWJsZWQiOnRydWUsInR5cGUiOiJ0ZXh0In0seyJrZXkiOiJwdWJsaWNfdG9rZW4iLCJ2YWx1ZSI6IiIsImVuYWJsZWQiOnRydWUsInR5cGUiOiJ0ZXh0In0seyJrZXkiOiJlbnZfdXJsIiwidmFsdWUiOiJzYW5kYm94LnBsYWlkLmNvbSIsImVuYWJsZWQiOnRydWUsInR5cGUiOiJ0ZXh0In0seyJrZXkiOiJhY2NvdW50X2lkIiwidmFsdWUiOiIiLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoidGV4dCJ9LHsia2V5IjoiYXNzZXRfcmVwb3J0X3Rva2VuIiwidmFsdWUiOiIiLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoidGV4dCJ9LHsia2V5IjoiYWNjZXNzX3Rva2VuIiwidmFsdWUiOiIiLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoidGV4dCJ9XQ==)
4. Once both the collection and the environment variables are imported into Postman, see the [Configuration](https://github.com/plaid/plaid-postman#configuration) section on how to correctly configure API keys with the collection.

### Configuration
The Plaid Postman collection uses [Postman environment variables](https://learning.getpostman.com/docs/postman/environments_and_globals/intro_to_environments_and_globals/) to simplify each API request. More information on managing Postman environments can be found at [Setting up an environment with variables](https://learning.getpostman.com/docs/postman/environments_and_globals/manage_environments/).

![plaid-postman-configuration](/images/plaid-postman-configuration.png)

1. Select the `Sandbox Public` environment in the top right corner
2. Click the `eye` icon to open the environment settings
3. Copy in your [Plaid API keys from your Plaid Dashboard](https://dashboard.plaid.com/account/keys), into each field:
  - `client_id`
  - `public_key`
  - `secret` (if you are using the Sandbox Public environment, this will be your Sandbox secret key)
4. Save your changes and start making Plaid API requests!

## Collection endpoints
The following collection is a fully-featured set of pre-filled requests that allow you to test the [Plaid API](https://plaid.com/docs), and visualize the responses in a friendly format.

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

## Making API calls

Most API calls require a [Plaid Token](https://plaid.com/docs/#plaid-tokens-public_token-access_token-or-asset_report_token)
in the form of an `access_token` (or an `asset_report_token` when dealing with
a [Plaid Asset](plaid.com/docs/#assets)).

Once you have imported and configured the requests, if, for example, you open
up the Retrieve Auth request and click "Send", you will get the following error:

![retrieve-auth-no-access-token](/images/retrieve-auth-no-access-token.png)

Opening up the Body tab of the request will reveal the issue:

![retrieve-auth-default-body](/images/retrieve-auth-default-body.png)

You can see that the supplied `access_token` is invalid, leading to the request
failing. How can you use the Postman Collection to generate a valid
`access_token`? You will need to emulate the
[Exchange Token Flow](https://plaid.com/docs/#exchange-token-flow) by first
using the following APIs:

- Create Item [Sandbox Only]
- Exchange Token

Then, you can begin using the generated `access_token` to make other API
requests.

### Create a Public Token

First, you need to [create a `public_token`](https://plaid.com/docs/#creating-public-tokens)
using the Create Item request. Simply open it up and click the "Send" button,
and you should see a response similar to the following:

![create-public-token](/images/create-public-token.png)

If you are going to need to use the [Assets API](https://plaid.com/docs/#assets),
then make sure you open up the Body tab of the request and add `"assets"` to the
`initial_products` array, and _then_ generate your token. Otherwise, your
`public_token` will not have the correct permissions set to use Assets:

![create-public-token-with-assets-product](/images/create-public-token-with-assets-product.png)

### Create an Access Token

Next, use the `public_token` you generated in the previous step to generate an
`access_token` with the Exchange Token request. Paste your `public_token` into
the `"public_token"` field into the Body section of the request. Click the
"Send" button, and you should see a response similar to the following:

![create-access-token-from-public-token](/images/create-access-token-from-public-token.png)

An `access_token` associated to an Item does not expire, so you can use it in
all of your requests. The Postman Collection has an `access_token` environment
variable field available where you can store your generated access token:

![add-access-token-to-env-variables](/images/add-access-token-to-env-variables.png)

### Use Access Token in API Calls

Now, go back to the Retrieve Auth request that failed earlier, open up the Body
of the request, and set the `access_token` field to be a reference to the access
token set in your environment variables by changing the value to be
`{{access_token}}`. Then, click the "Send" button, and you should see a
successful response.

![retrieve-auth-with-access-token](/images/retrieve-auth-with-access-token.png)

You can now repeat this step for any other Plaid API that requires an
`access_token`.

### Create an Asset Report Token

As well as using `access_tokens`, Plaid Asset Reports have their own
`asset_report_token` that need to be used when using the Retrieve an Asset
Report request. You generate an `asset_report_token` using the Create Asset
Report request.

Open up the Body tab of the request, and add the reference to your access token
(`{{access_token}}`) to the array in the `access_tokens` field. Then, click the
"Send" button, and you should see a response similar to the following:

![create-asset-report-token-with-access-token](/images/create-asset-report-token-with-access-token.png)

(The `options` object that is included by default in the Body was removed here
for brevity).

Similar to an `access_token`, an `asset_report_token` also does not expire, so
you can use it in all of your asset report-related requests. The Postman
Collection has an `asset_report_token` environment variable field available
where you can store your generated token:

![add-asset-report-token-to-env-variables](/images/add-asset-report-token-to-env-variables.png)

### Use Asset Report Token in API Calls

Now, you can try an API request like the Retrieve an Asset Report (JSON) request,
which requires an `asset_report_token`. Open up the Body of the request, and set
the `asset_report_token` field to be a reference to the asset report token set
in your environment variables by changing the value to be
`{{asset_report_token}}`. Then, click the "Send" button, and you should see a
successful response.

![retrieve-asset-report-with-asset-report-token](/images/retrieve-asset-report-with-asset-report-token.png)

## Useful Tools
[Webhook Tester](https://webhook.site/) is a great tool for receiving webhook calls. Generate a webhook url on this site and use that url for any Postman requests that require you to specify a webhook url. You can go on Webhook Tester to see a list of all requests being made to that url.


## Important Note
The `/public_token/create` endpoint is only available in the `sandbox` environment. It exists only for testing purposes and simulates an Item Creation via the Plaid Link module. Items cannot be created directly via an endpoint for the `development` and `production` environments and can only be created through Plaid Link.
