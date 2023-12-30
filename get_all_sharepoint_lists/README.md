## Power Automate Cloud Flow Documentation

### How to use?
Copy the json payload in the file "flow.json" for each Main Flow and Exception Handler and insert it via STRG+V into your flow. Adjust all missing connections.
<img src="https://i.imgur.com/OAp9qCC.gif"/>

### Important note
Be sure that you configure the Exception Handler Scope to "run only" after the main scope has failed. Otherwise the exception handler will run all the time, which is not intended.
See here:
<img src="https://i.imgur.com/eE8yKKi.png"/>

### Prequisitions:
Create a manual trigger (e.g. Power Apps V2) and create an input of the type Text with the name "SharePointSite" in this trigger. In this you will later transfer the URl for the specific SharePoint site on which the lists are to be looked up.
<img src="https://i.imgur.com/2gWdfVs.png"/>

### Main Flow (`2f95a401-ecdb-45c0-8dae-cc5fef6fe10b`)
- **Purpose**: Retrieves all visible SharePoint lists from a specified site.
- **Actions**:
  1. **Send HTTP Request to SharePoint**: Retrieves lists from a SharePoint site.
  2. **Filter Array**: Excludes hidden lists.
  3. **Select**: Gathers titles, item counts, IDs, and created timestamps of lists.
  4. **Respond to a PowerApp or Flow**: Returns the gathered list information.

### Exception Handler (`de744fe8-c603-4ead-9d81-f401b0240660`)
- **Purpose**: Handles any errors from the main flow.
- **Actions**:
  1. **Send an Email (V2)**: Notifies about the error.
  2. **Terminate**: Ends the flow if there's an error.
  3. **Create HTML Table**: Summarizes errors.
  4. **Respond to PowerApp or Flow**: Informs about the error.
