

## Power Automate Cloud Flow Documentation

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

#### Main Flow (ID: 6220c582-319e-433e-8466-69ea536d8ed5)

**Purpose:** Retrieves and sends all views from a specified SharePoint list, focusing on visible and relevant view details.

**Actions:**
1. **Send HTTP Request to SharePoint | Get All Views:** Fetches all views from the given SharePoint list.
2. **Select:** Filters the retrieved views data to extract necessary details including ID, Title, DefaultView, and ViewFieldsUri.
3. **Respond to PowerApp or Flow:** Sends the curated list of views and a success status back to the calling PowerApp or Flow.

#### Exception Handler (ID: b8af0d7b-da37-4e2a-ab0e-3ee963c0004b)

**Purpose:** Manages and notifies of any errors occurring in the main flow.

**Actions:**
1. **Send Email (V2) | Send Mail to Exception Receiver:** Informs designated personnel of the error via email, providing technical details and links for troubleshooting.
2. **Terminate:** Stops the flow if an error is encountered, ensuring no further actions are taken.
3. **Create HTML Table | Create Table with Errors:** Structures error details into an HTML table for clarity in the notification email.
4. **Respond to PowerApp or Flow | Respond Error:** Notifies the initiating PowerApp or flow of the error for user awareness.
