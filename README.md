# Plaid Postman Collections
Welcome to the Postman Collections Quickstart Guide! If you're looking for a quick and easy way to get started with the Plaid API with no additional code, this is the place for you.

For the Plaid Quickstart guide that uses code, see the [Plaid Quickstart](https://github.com/plaid/quickstart).

## Getting started
Follow these steps to quickly get started with the [Plaid API](https://plaid.com/docs):

1. [Sign up](https://dashboard.plaid.com/signup) with Plaid to get a set of API keys that are required for interacting with the API.
2. Click the "Run in Postman" button below.
  
[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/300b6d41be01cbd6a882?action=collection%2Fimport)

3. Once both the collection and the environment variables are imported into Postman, see the [Configuration](https://github.com/plaid/plaid-postman#configuration) section on how to correctly configure API keys with the collection.

### Configuration
The Plaid Postman collection uses [Postman environment variables](https://learning.getpostman.com/docs/postman/environments_and_globals/intro_to_environments_and_globals/) to simplify each API request. More information on managing Postman environments can be found at [Setting up an environment with variables](https://learning.getpostman.com/docs/postman/environments_and_globals/manage_environments/).

![plaid-postman-configuration](/images/plaid-postman-config.png)

1. Select the `Sandbox Public` environment in the top right corner
2. Click the `eye` icon to open the environment settings
3. Copy in your [Plaid API keys from your Plaid Dashboard](https://dashboard.plaid.com/account/keys), into each field:
  - `client_id`
  - `secret`
4. Save your changes and start making Plaid API requests!

## Quickstart

Once you have completed the steps in the Configuration section above, you are ready to make API requests using Postman! The following steps are a quick walkthrough to making an API request. In this example, we will use the special capabilities of the Sandbox test environment to bypass the client-side Link UI and make all of our requests via the backend. 

1. Make sure the "Collection" pane is selected, then expand the "Plaid API Endpoints" folder on the left and navigate to Plaid API Endpoints -> Items -> Create Item[Sandbox only].
2. In the pane on the right, which has the options "Params", "Authorization", "Headers" etc. click on the "Body" tab. 
3. If you want, update the product under `initial_products` to match the product you would like to try, such as "transactions" or "identity". Otherwise, click the blue "Send" button on the right.
4. The response body should appear in Postman. Copy the `public_token` value (for example, "public-sandbox-00c6acae-9aab-4c3b-9f2d-d1ea710f3103"). 
5. Select the "Exchange token" endpoint, click on the "Body" tab, and paste your public token into the request, then hit "Send".
6. Copy the `access_token` value (for example, "access-sandbox-0128b38c-3219-4f8b-827a-c2e42b19c125").
7. Select any product endpoint of your choice. If you are not sure which one to use, a good simple example is "Balance". Expand the product endpoint folder and click on the endpoint you would like to use ("Retrieve Balance", if we are using balance). 
8. Click on the "Body" tab. Paste your access token into the `access_token` field. Complete any other required fields (for Balance, there are none) and click Send.
9. You will receive a response containing your requested data!

## Collection endpoints
The following collection is a fully-featured set of pre-filled requests that allow you to test the [Plaid API](https://plaid.com/docs), and visualize the responses in a friendly format.

* **Link Tokens**
  * **Create Link Token** - Creates a `link_token` for the default Link flow.
  * **Create Link Token - Update Mode** - Creates a `link_token` for the update mode Link flow.
  * **Create Link Token - Payment Initiation** - Creates a `link_token` for the payment initiation Link flow.
  * **Create Link Token - OAuth** - Creates a `link_token` for the OAuth Link flow.

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

* **Income / Employment**
  * **Income Item Creation** - Simulate creating an Income Item in Sandbox without going through the actual user Link experience.
  * **Retrieve Paystubs Info** - Retrieve paystubs related data from user's income verification
  * **Retrieve Taxform Data** - Retrieve taxforms (W2, etc.) related data from user's income verification
  * **Retrieve Employment Info** - Retrieve employment related data (job title, starting date) from user's payroll information

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
