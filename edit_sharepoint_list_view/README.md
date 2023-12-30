### Power Automate Cloud Flow Documentation

### How to use?
Copy the json payload in the file "flow.json" for each Main Flow and Exception Handler and insert it via STRG+V into your flow. Adjust all missing connections.
<img src="https://i.imgur.com/OAp9qCC.gif"/>

### Important note
Be sure that you configure the Exception Handler Scope to "run only" after the main scope has failed. Otherwise the exception handler will run all the time, which is not intended.
See here:

<img src="https://i.imgur.com/eE8yKKi.png"/>

### Prequisitions:
Create a manual trigger (e.g. Power Apps V2) and create an input of the type Text with the name "SharePoint_Site" in this trigger and another one "SharePoint_List" and "SharePoint_List_View". In SharePoint_Site you will later transfer the URl for the specific SharePoint site on which the lists are to be looked up. In "SharePoint_List" you insert the Id of the specific List you want to retrieve views from. To retrieve SharePoint List Ids via Power Automate see this cloud flow: https://github.com/einfachKim/powerplatformhacks/tree/main/get_all_sharepoint_lists. In "SharePoint_List_View" you need to insert the Id of the specific view you want to modifiy. To retrieve SharePoint List View Ids via Power Automate see this cloud flow: https://github.com/einfachKim/powerplatformhacks/tree/main/get_all_list_views

<img src="https://i.imgur.com/4YuGmze.png"/>


### Main Flow (ID: c2af734d-8ee3-4576-b592-f760b1558b86)
**Purpose:** Customize a selected SharePoint view by applying a filter on ID = 0.

**Actions:**
1. **Send HTTP Request to SharePoint:** Modifies the view using a POST request with MERGE method to apply ViewQuery that filters items where ID equals 0.
2. **Respond to PowerApp or Flow:** Sends a status notification back to the PowerApp or flow confirming the successful execution.

### Exception Handler (ID: 365d8184-ca60-4568-bd8f-b7bbdabadc18)
**Purpose:** Manages exceptions by notifying users and providing error details.

**Actions:**
1. **Send Email (V2):** Alerts a designated receiver about the flow failure with detailed information and links.
2. **Create HTML Table:** Compiles error details into an HTML table format.
3. **Terminate:** Ends the flow marking it as failed.
4. **Respond to PowerApp or Flow:** Informs the initiating app or flow of the error and actions taken.
