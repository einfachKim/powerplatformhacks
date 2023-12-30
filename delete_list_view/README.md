### Power Automate Cloud Flow Documentation

### How to use?
Copy the json payload in the file "flow.json" for each Main Flow and Exception Handler and insert it via STRG+V into your flow. Adjust all missing connections.
<img src="https://i.imgur.com/M8WPxHo.gif"/>

### Important note
Be sure that you configure the Exception Handler Scope to "run only" after the main scope has failed. Otherwise the exception handler will run all the time, which is not intended.
See here:

<img src="https://i.imgur.com/eE8yKKi.png"/>

### Prequisitions:
Create a manual trigger (e.g. Power Apps V2) and create an input of the type Text with the name "SharePoint_Site" in this trigger and another one "SharePoint_List" and "SharePoint_List_View". In SharePoint_Site you will later transfer the URl for the specific SharePoint site on which the lists are to be looked up. In "SharePoint_List" you insert the Id of the specific List you want to retrieve views from. To retrieve SharePoint List Ids via Power Automate see this cloud flow: https://github.com/einfachKim/powerplatformhacks/tree/main/get_all_sharepoint_lists. In "SharePoint_List_View" you need to insert the Id of the specific view you want to modifiy. To retrieve SharePoint List View Ids via Power Automate see this cloud flow: https://github.com/einfachKim/powerplatformhacks/tree/main/get_all_list_views

<img src="https://i.imgur.com/4YuGmze.png"/>

### Main Flow (ID: 60e390bb-73fc-4e67-a21e-a545613d05f7)
**Purpose:** Deletes a specific view from a SharePoint list.

**Actions:**
1. **Send HTTP Request to SharePoint:** Performs a DELETE operation targeting a specific SharePoint list view. https://i.imgur.com/BepmNW2.png
2. **Respond to PowerApp or Flow:** Confirms successful deletion by returning a status message.

### Exception Handler (ID: 52ed02e0-0c5b-4452-8827-61e0e6d5b992)
**Purpose:** Manages any errors during the deletion process.

**Actions:**
1. **Send Email (V2):** Alerts a specified recipient of the error with detailed information.
2. **Create HTML Table:** Summarizes error details for easier understanding.
3. **Terminate:** Ends the flow if an error is encountered.
4. **Respond to PowerApp or Flow:** Informs the initiating application of the error.
