### Power Automate Cloud Flow Documentation

### How to use?
Copy the json payload in the file "flow.json" for each Main Flow and Exception Handler and insert it via STRG+V into your flow. Adjust all missing connections.
<img src="https://i.imgur.com/M8WPxHo.gif"/>

### Important note
Be sure that you configure the Exception Handler Scope to "run only" after the main scope has failed. Otherwise the exception handler will run all the time, which is not intended.
See here:

<img src="https://i.imgur.com/eE8yKKi.png"/>

### Prequisitions:
Create a manual trigger (e.g. Power Apps V2) and create an input of the type Text with the name "SharePoint_Site" in this trigger and another one "SharePoint_ViewFieldsURI". The first one contains the URL for the specific SharePoint Website.
The Latter is the specific endpoint for the fields within this view. See this cloud flow on how to retrieve ViewFieldsURI: https://github.com/einfachKim/powerplatformhacks/blob/main/get_all_list_views/README.md#:~:text=Select%3A%20Filters,the%20key%20%22ViewFieldsUri%22.
See also here: https://i.imgur.com/FmSXPsG.png

<img src="https://i.imgur.com/MOnWHI0.png"/>


### Main Flow (ID: 068929a8-31d4-470f-96d8-27035c54c7c4)
**Purpose:** Retrieves specific SharePoint view fields based on provided site and view field URI.

**Actions:**
1. **Send HTTP Request to SharePoint:** Fetches fields for a given SharePoint view, applying necessary filters or conditions.
2. **Select:** Structures the fetched field data for further use or display.
3. **Respond to PowerApp or Flow:** Returns the processed fields data and a success status to the initiating PowerApp or Flow.

### Exception Handler (ID: 0266d335-2bdc-4c86-bbca-a99745d5801c)
**Purpose:** Manages any errors occurring in the main flow, ensuring users and administrators are notified.

**Actions:**
1. **Send Email (V2):** Informs a designated receiver about the flow failure with detailed information.
2. **Create HTML Table:** Summarizes error details for the notification email.
3. **Terminate:** Ends the flow marking it as failed, preventing any further erroneous operations.
4. **Respond to PowerApp or Flow:** Notifies the initiating app or flow about the error, ensuring transparency and prompt attention to the issue.
