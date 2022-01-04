# Plaid Postman Collections
Welcome to the Postman Collections Quickstart Guide! If you're looking for a quick and easy way to get started with the Plaid API with no additional code, this is the place for you.

For the Plaid Quickstart guide that uses code, see the [Plaid Quickstart](https://github.com/plaid/quickstart).

## Getting started
Follow these steps to quickly get started with the [Plaid API](https://plaid.com/docs):

1. [Sign up](https://dashboard.plaid.com/signup) with Plaid to get a set of API keys that are required for interacting with the API.
2. Click the "Run in Postman" button below.
  
[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/300b6d41be01cbd6a882?action=collection%2Fimport#?env%5BSandbox%5D=dW5kZWZpbmVk)

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

1. Make sure the "Collection" pane is selected, then expand the "Plaid API Endpoints" folder on the left and navigate to Plaid API Endpoints -> Items -> Item Creation -> Create Item [Sandbox Only].
2. In the pane on the right, which has the options "Params", "Authorization", "Headers" etc. click on the "Body" tab. 
3. (Optional) If you want, update the product under `initial_products` to match the product you would like to try, such as "transactions" or "identity". 
4. Click the blue "Send" button on the right.
5. The response body should appear in Postman. The `public_token` returned will automatically be used in our next request.
6. Select the "Exchange token" endpoint, click on the "Body" tab, then hit "Send". An `access_token` will be returned and will automatically be used in our next request.

7. Select any product endpoint of your choice. If you are not sure which one to use, a good simple example is "Balance". Expand the product endpoint folder and click on the endpoint you would like to use ("Retrieve Balance", if we are using balance).

8. Click on the "Body" tab. Complete any other required fields (for Balance, there are none) and click "Send".
9. You will receive a response containing your requested data!

## Making Postman calls with real data in Production or Development

For reasons of security and transparency, getting an access token for use with real data cannot be done entirely via Postman API calls -- you are required to use the Plaid Link UI component. You can do this as follows:

1. Download the [link.html](/link.html) file included in this repo and open it in a text editor (alternatively, open a text editor, create a new file called link.html, and copy and paste the contents of [link.html](/link.html) into it). You will use this file later.
2. Re-visit the "Configuration" steps at the top of this page, but instead change the `client_id` and `secret_key` environment variables to your client ID and secret for Production (or Development) instead of for Sandbox, then set the `env_url` environment variable to `production.plaid.com` (for Production) or `development.plaid.com` (for Development).
3. Navigate to Plaid API Endpoints -> Link Tokens -> Create Link Token and click on the "Body" tab.
4. If you want, replace "auth" with the name of the product you would like to try, such as "transactions" or "identity". 
5. Click the blue "Send" button.
6. Copy the value of the `link_token` from the response.
7. Return to your local copy of link.html. Replace the text 'your-link-token-goes-here' in link.html with the value you copied in the previous step, and save the file.
8. Open link.html in a web browser.
9. Open the web browser Developer Tools (for example, in Chrome, go to View->Developer->Developer Tools), then open the Console tab within Developer tools.
10. Click the "Link Account" button on link.html to launch Link. The Plaid Link component should launch. Follow the prompts and log into a financial institution.
11. Once the prompts have completed and you have successfully logged in via Link, the Console tab from step 8 should contain text saying "the public token is" and then the value of the public token. Copy the public token value.
12. Return to Postman and go to API Endpoints -> Item Creation -> Exchange Token, click on the Body tab, and select the public token value -- by default, it is `"{{public_token}}"`. Replace this value with your copied public token from the previous step, then hit Send.
13. The response will contain an `access_token` suitable for making calls in Production (or Development)! You can then follow the same steps as you did in the Quickstart (starting with step 7) to make API requests for real data.

## Useful Tools
[Webhook Tester](https://webhook.site/) and [Request Bin](https://requestbin.com/) are useful tools for receiving webhook calls. You can use them to generate a webhook url and use that url for any Postman requests that require you to specify a webhook url, then use the sites to inspect the content of any webhooks they received.
