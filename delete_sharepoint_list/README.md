### SharePoint List Deletion Flow Documentation

### How to use?
Copy the json payload in the file "flow.json" for each Main Flow and Exception Handler and insert it via STRG+V into your flow. Adjust all missing connections.
<img src="https://i.imgur.com/OAp9qCC.gif"/>

### Important note
Be sure that you configure the Exception Handler Scope to "run only" after the main scope has failed. Otherwise the exception handler will run all the time, which is not intended.
See here:

<img src="https://i.imgur.com/eE8yKKi.png"/>


### Prequisitions:
Create a manual trigger (e.g. Power Apps V2) and create an input of the type Text with the name "SharePoint_Site" in this trigger and another one "SharePoint_List". In SharePoint_Site you will later transfer the URl for the specific SharePoint site on which the lists are to be looked up. In "SharePoint_List" you insert the Id of the specific List you want to retrieve views from. To retrieve SharePoint List Ids via Power Automate see this cloud flow: https://github.com/einfachKim/powerplatformhacks/tree/main/get_all_sharepoint_lists

<img src="https://i.imgur.com/jrwO7NT.png"/>


#### Purpose
This flow is designed to delete a specific SharePoint list based on given parameters.

#### Actions
1. **Send HTTP Request to SharePoint**: Executes a DELETE request to remove a specified SharePoint list using its unique identifier.
2. **Respond to PowerApp or Flow**: Sends a status message back to the PowerApp or flow to confirm the action's success or failure.

The exception handler provides a robust error management mechanism, sending email alerts for failures and logging detailed information for troubleshooting purposes.
