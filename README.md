# Plaid Postman Collections

Welcome to the Postman Collections Quickstart Guide! If you're looking for a quick and easy way to get started with the Plaid API with no additional code, this is the place for you.

If you're not interested in reading these instructions, you can go directly to [the Plaid Postman collection](https://www.postman.com/plaid-api/workspace/plaid/collection/12160321-04d27ed8-aed4-4d46-a1f8-70a72ec9a78a).

For the Plaid Quickstart guide that uses code, see the [Plaid Quickstart](https://github.com/plaid/quickstart).

Don't feel like reading? Check out our [Plaid and Postman in Three Minutes Quickstart video](https://www.youtube.com/watch?v=f4NhgHpp5aA). Or, for a more detailed walkthrough, watch the [Plaid Postman Full tutorial video](https://www.youtube.com/watch?v=dJds8Qc7weQ).

## Table of contents

- [Getting started](#getting-started)
  - [Configuration](#configuration)
- [Making API calls in Sandbox](#making-api-calls-in-sandbox)
  - [Income](#income)
  - [Identity Verification and Monitor](#identity-verification-and-monitor)
  - [Layer](#layer)
- [Making API calls with real data in Production](#making-api-calls-with-real-data-in-production)
- [Webhook testing tools](#webhook-testing-tools)

## Getting started

Follow these steps to quickly get started with the [Plaid API](https://plaid.com/docs):

1. [Sign up](https://dashboard.plaid.com/signup) with Plaid to get a set of API keys that are required for interacting with the API.
2. Click the "Run in Postman" button below, and then click the "Fork Collection" button when prompted. You will be required to create a free account with Postman. 

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/12160321-04d27ed8-aed4-4d46-a1f8-70a72ec9a78a?action=collection%2Ffork&collection-url=entityId%3D12160321-04d27ed8-aed4-4d46-a1f8-70a72ec9a78a%26entityType%3Dcollection%26workspaceId%3Dfbafb5a2-25a1-482a-a65b-1f637a19ed49#?env%5BSandbox%5D=W3sia2V5IjoiY2xpZW50X2lkIiwidmFsdWUiOiJZT1VSX0NMSUVOVF9JRCIsImVuYWJsZWQiOnRydWUsInR5cGUiOiJzZWNyZXQiLCJzZXNzaW9uVmFsdWUiOiI2MmFiN2FhNjMxYmY1MDAwMTI1ZDQxMjQiLCJzZXNzaW9uSW5kZXgiOjB9LHsia2V5Ijoic2VjcmV0X2tleSIsInZhbHVlIjoiWU9VUl9TRUNSRVQiLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoic2VjcmV0Iiwic2Vzc2lvblZhbHVlIjoiWU9VUl9TRUNSRVQiLCJzZXNzaW9uSW5kZXgiOjF9LHsia2V5IjoicHVibGljX3Rva2VuIiwidmFsdWUiOiIiLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoidGV4dCIsInNlc3Npb25WYWx1ZSI6IiIsInNlc3Npb25JbmRleCI6Mn0seyJrZXkiOiJhY2Nlc3NfdG9rZW4iLCJ2YWx1ZSI6IiIsImVuYWJsZWQiOnRydWUsInR5cGUiOiJ0ZXh0Iiwic2Vzc2lvblZhbHVlIjoiIiwic2Vzc2lvbkluZGV4IjozfSx7ImtleSI6ImFzc2V0X3JlcG9ydF90b2tlbiIsInZhbHVlIjoiIiwiZW5hYmxlZCI6dHJ1ZSwidHlwZSI6InRleHQiLCJzZXNzaW9uVmFsdWUiOiIiLCJzZXNzaW9uSW5kZXgiOjR9LHsia2V5IjoiZW52X3VybCIsInZhbHVlIjoic2FuZGJveC5wbGFpZC5jb20iLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoidGV4dCIsInNlc3Npb25WYWx1ZSI6InNhbmRib3gucGxhaWQuY29tIiwic2Vzc2lvbkluZGV4Ijo1fSx7ImtleSI6ImFjY291bnRfaWQiLCJ2YWx1ZSI6IiIsImVuYWJsZWQiOnRydWUsInR5cGUiOiJ0ZXh0Iiwic2Vzc2lvblZhbHVlIjoiIiwic2Vzc2lvbkluZGV4Ijo2fSx7ImtleSI6InByb2Nlc3Nvcl90b2tlbiIsInZhbHVlIjoiIiwiZW5hYmxlZCI6dHJ1ZSwidHlwZSI6InRleHQiLCJzZXNzaW9uVmFsdWUiOiIiLCJzZXNzaW9uSW5kZXgiOjd9LHsia2V5IjoidHJhbnNmZXJfaWQiLCJ2YWx1ZSI6IiIsImVuYWJsZWQiOnRydWUsInR5cGUiOiJ0ZXh0Iiwic2Vzc2lvblZhbHVlIjoiIiwic2Vzc2lvbkluZGV4Ijo4fSx7ImtleSI6InVzZXJfdG9rZW4iLCJ2YWx1ZSI6IiIsImVuYWJsZWQiOnRydWUsInR5cGUiOiJ0ZXh0Iiwic2Vzc2lvblZhbHVlIjoiIiwic2Vzc2lvbkluZGV4Ijo5fSx7ImtleSI6InVzZXJfaWQiLCJ2YWx1ZSI6IiIsImVuYWJsZWQiOnRydWUsInR5cGUiOiJ0ZXh0Iiwic2Vzc2lvblZhbHVlIjoiIiwic2Vzc2lvbkluZGV4IjoxMH0seyJrZXkiOiJwYXltZW50X2NvbnNlbnRfaWQiLCJ2YWx1ZSI6IiIsImVuYWJsZWQiOnRydWUsInR5cGUiOiJhbnkiLCJzZXNzaW9uVmFsdWUiOiIiLCJzZXNzaW9uSW5kZXgiOjExfSx7ImtleSI6ImxpbmtfdG9rZW4iLCJ2YWx1ZSI6IiIsImVuYWJsZWQiOnRydWUsInR5cGUiOiJhbnkiLCJzZXNzaW9uVmFsdWUiOiIiLCJzZXNzaW9uSW5kZXgiOjEyfSx7ImtleSI6ImNsaWVudF90cmFuc2FjdGlvbl9pZCIsInZhbHVlIjoiIiwiZW5hYmxlZCI6dHJ1ZSwidHlwZSI6ImFueSIsInNlc3Npb25WYWx1ZSI6InlvdXJfdW5pcXVlX2lkZW50aWZpZXJfZ29lc19oZXJlIiwic2Vzc2lvbkluZGV4IjoxM31d)

3. Once both the collection and the environment variables are imported into Postman, see the [Configuration](https://github.com/plaid/plaid-postman#configuration) section on how to correctly configure API keys with the collection.

### Configuration

The Plaid Postman collection uses [Postman environment variables](https://learning.getpostman.com/docs/postman/environments_and_globals/intro_to_environments_and_globals/) to simplify each API request.

![plaid-postman-configuration](/images/plaid-postman-config.png)

1. Select the `Sandbox` environment in the top right corner
2. Click the `eye` icon to open the environment settings
3. Copy in your [Plaid API keys from your Plaid Dashboard](https://dashboard.plaid.com/developers/keys), into each field:

- `client_id`
- `secret`

4. Save your changes and start making Plaid API requests!

## Making API calls in Sandbox

Once you have completed the steps in the [Configuration](#configuration) section above, you are ready to make API requests using Postman! The following steps are a quick walkthrough to making an API request. In this example, we will use the special capabilities of the Sandbox test environment to bypass the client-side Link UI and make all of our requests via the backend.

1. Make sure the "Collection" pane is selected, then expand the "Plaid API Endpoints" folder on the left and navigate to Plaid API Endpoints -> Items -> Item Creation -> Create Item [Sandbox Only].
2. In the pane on the right, which has the options "Params", "Authorization", "Headers" etc. click on the "Body" tab.
3. (Optional) If you want, update the product under `initial_products` to match the product you would like to try, such as "transactions" or "identity".
4. Click the blue "Send" button on the right.
5. The response body should appear in Postman. The `public_token` returned will automatically be used in our next request.
6. Select the "Exchange token" endpoint, click on the "Body" tab, then hit "Send". An `access_token` will be returned and will automatically be used in our next request.
7. Select any product endpoint of your choice. If you are not sure which one to use, a good simple example is "Balance". Expand the product endpoint folder and click on the endpoint you would like to use ("Retrieve Balance", if you are using balance).
8. Click on the "Body" tab. Complete any other required fields (for Balance, there are none) and click "Send".
9. You will receive a response containing your requested data!

### Income

Testing the Payroll Income or Document Income flows requires modifying the steps above. Instead of calling "Create Item [Sandbox Only]", go to the Income folder and call "Create User Token", followed by "Initialize User Token for Payroll Income [Sandbox only]", or "Initialize User Token for Bank Income [Sandbox only]" as appropriate, and then finally "Retrieve Payroll Income" or "Retrieve Bank Income".

### Plaid Check Consumer Reports

New customers are not enabled for Consumer Reports by default. Submit an [Access Request](https://dashboard.plaid.com/support/new/product-and-development) or [contact Sales](http://www.plaid.com/contact) to use the Postman collection.

Testing the Plaid Check Consumer Reports flows requires modifying the steps above. Instead of calling "Create Item [Sandbox Only]", go to the Plaid Check folder and call "Create User Token", followed by "Create Link Token". Next, following the instructions for [Making API calls with real data in Production](#making-api-calls-with-real-data-in-production), paste this Link token into the link.html file and go through the Link flow; you do not need to complete steps 13-15, as a public token is not needed for Consumer Reports. Once you have completed the Link flow, you can make API calls to Consumer Report endpoints such as `/cra/check_report/base_report/get`.

### Identity Verification and Monitor

New Plaid customers are not enabled for Identity Verification or Monitor in the Sandbox by default. Submit an [Access Request](https://dashboard.plaid.com/support/new/product-and-development) or [contact Sales](http://www.plaid.com/contact) to use the Postman collection.

Identity Verification and Monitor cannot be tested using the instructions above. To test Identity Verification or Monitor, use the instructions below for [making Postman calls with real data](#making-api-calls-with-real-data-in-production); but you may optionally use Sandbox instead of Production. 

In order to call `/link/token/create` in step 6 below when using Identity Verification, use the "Plaid API Endpoints -> Link Tokens -> Create Link Token (Identity Verification)" endpoint. You will need to provide a `template_id` in the `identity_verification` object. This id can be obtained from the Dashboard -- in the upper-left corner, select **Identity Verification and Monitor** from the team selection drop-down list (if this does not exist, make sure to submit a product access request). Under **Identity Verification**, click the **Integration** button, and copy the `template_id.` 

You do not need to complete steps 13-15 below, as a public token is not needed for Identity Verification or Monitor; instead, you can view the status of the verification within the Dashboard.

### Layer

New Plaid customers are not enabled for Layer in the Sandbox by default. Submit an [Access Request](https://dashboard.plaid.com/support/new/product-and-development) or [contact Sales](http://www.plaid.com/contact) to use the Postman collection.

Layer cannot be tested using the instructions above. To test Layer, use the instructions below for [making Postman calls with real data](#making-api-calls-with-real-data-in-production); but you may optionally use Sandbox instead of Production. 

Once you have obtained the public token, instead of following steps 14-15 to exchange it for an access token, call `/user_account/session/get`.

## Making API calls with real data in Production

> [!IMPORTANT]  
> To use Plaid in Production, you must first add a Link use case in the Dashboard, under [Link->Customization->Data Transparency](https://dashboard.plaid.com/link/data-transparency-v5).


For reasons of security and transparency, getting an access token for use with real data cannot be done entirely via Postman API calls -- you are required to use the Plaid Link UI component to obtain a `public_token`, which you can then feed back into Postman. You can do this as follows:

1. Download the [link.html](/link.html) file included in this repo and open it in a text editor (alternatively, open a text editor, create a new file called link.html, and copy and paste the contents of [link.html](/link.html) into it). You will use this file later.
2. Re-visit the "Configuration" steps at the top of this page, but after opening the environment settings, click the "..." button in the upper right and select "Duplicate". This will create a new environment called "Sandbox copy" -- to rename it, click the pencil icon next to the name and name it "Production".
3. On your newly created environment, change the `client_id` and `secret_key` environment variables to your client ID and secret for Production instead of for Sandbox, then set the `env_url` environment variable to `production.plaid.com`.
4. To apply these new settings, select your new environment from the drop-down in the upper right. Alternatively, while editing the new environment, you can click "..." and select "Set as active environment".
5. Navigate to Plaid API Endpoints -> Link Tokens -> Create Link Token and click on the "Body" tab.
6. If you want, replace "auth" with the name of the product you would like to try, such as "transactions" or "identity". Note that only institutions that support ALL the products you specify here will appear in Link -- if you don't see the institution you want when Link is launched, make sure you have listed the right product. For example, an institution that only supports credit cards (e.g. American Express) will not appear in Link if a product that doesn't support credit cards (like auth) is specified.
7. Click the blue "Send" button.
8. Copy the value of the `link_token` from the response.
9. Return to your local copy of link.html. Replace the text 'your-link-token-goes-here' in link.html with the value you copied in the previous step, and save the file.
10. Open link.html in a web browser.
11. Open the web browser Developer Tools (for example, in Chrome, go to View->Developer->Developer Tools), then open the Console tab within Developer tools.
12. Click the "Link Account" button on link.html to launch Link. The Plaid Link component should launch. Follow the prompts and log into a financial institution. Make sure to use a real username and password, not the Sandbox credentials.
13. Once the prompts have completed and you have successfully logged in via Link, the Console tab should contain text saying "the public token is:" followed by the value of the public token. Copy the public token value.
14. Return to Postman and go to API Endpoints -> Item Creation -> Exchange Token, click on the Body tab, and select the public token value -- by default, it is `{{public_token}}`. Replace this value with your copied public token from the previous step, making sure the token value is inside the quotation marks, then hit Send.
15. The response will contain an `access_token` suitable for making calls in Production! As in the [Making API calls in Sandbox](#making-api-calls-in-sandbox) directions, it will be automatically saved for you to use in future requests. You can then follow the same steps as you did in the that section (starting with step 7) to make API requests for real data.

## Webhook testing tools

[Webhook Tester](https://webhook.site/) and [Request Bin](https://requestbin.com/) are useful tools for receiving webhook calls. You can use them to generate a webhook url and use that url for any Postman requests that require you to specify a webhook url, then use the sites to inspect the content of any webhooks they received.
