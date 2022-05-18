This documentation is primarily aimed at Plaid employees who would like to edit the collection. For instructions on using the collection, see the README.

#### Editing the Plaid Postman collection
The easiest way to edit the collection is to edit your own local copy of the collection using the Postman app. After downloading it, you can open the Plaid Postman collection and make edits. This is a pretty intuitive process, with a few things to be aware of:

Make sure to use the "tests" tab of the collection when appropriate to save values that will be used as input to other API calls. For example, when calling `/link/token/create`, we have the following under "tests":

```
let response = pm.response.json();
linkToken = response.link_token;
pm.environment.set("link_token", linkToken);
```

This code allows other API calls to reference ``{{link_token}}`` in the request body rather than requiring the user to copy and paste the Link token.

Make sure to rename examples to "OK" rather than using the default name.

#### Publishing the Plaid Postman collection

**Important: Before you publish the collection, make sure to clear the values of all environment variables except for the ones that were set before you downloaded the collection.**

When you are ready to publish the collection, do the following:

Click on the "..." next to the collection name and select "export" and then "Collection 2.1". Rename the resulting JSON file to match the name of the file used on GitHub (currently "Plaid API Endpoints Collection.json") and add it to your commit. While this JSON file isn't used by Postman directly, it's a good way to keep track of your changes within GitHub.

Click on the "..." next to the collection name and click "share" -> "Via run in Postman" -> "Embed a static version" -> "Generate code" -> "Add an environment" (select Sandbox) -> "Markdown friendly" 

Test the link generated to make sure it works correctly! If it doesn't, try restarting Postman and following the steps above. If it does work, copy and paste the markdown into the README, replacing the old button. Add the README to your commit.

Once your commit has been approved and you have merged your changes, copy the collection to the [Plaid Postman workspace](https://www.postman.com/plaid-api/workspace/plaid/collection/12160321-029fcda5-4c0c-478f-8fe4-0431f99e213e), overwriting the existing collection there, to update the version of the collection hosted on Postman. If you are not a member of the Plaid workspace, there should be a button in the Postman UI to request to join. If you can't find it, contact someone in DevRel.

#### Resolving Merge Conflicts
If someone merges to `master` before you land your changes, you may clobber their changes if you don't find a way to incorporate them.

Suggested course of action:
1. Merge `origin/master` into your branch. The Plaid API Endpoints Collection JSON should merge cleanly, incorporating new changes with your unmerged changes, EXCEPT for the `_postman_id`, which is fine. We will regenerate this in the next step.
1. Import the Postman collection from the merged Plaid API Endpoints Collection JSON. You should replace the existing postman collection (since we want the collection to have the same name).
1. From here, everything in the GUI is good to go and you should proceed as normal in [publishing the Plaid Postman collection](####publishing-the-plaid-postman-collection)
  - Re-export the Postman collection to the Plaid API Endpoints Collection JSON (fixes the `_postman_id`)
  - Fix the README button (regenerate within Postman + replace in README)
