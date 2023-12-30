## Power Automate Cloud Flow Documentation

## How to use?
Copy the json payload in the file "flow.json" for each Main Flow and Exception Handler and insert it via STRG+V into your flow. Adjust all missing connections.
<img src="https://i.imgur.com/aTiIdZO.gif"/>

### Important note
Be sure that you configure the Exception Handler Scope to "run only" after the main scope has failed. Otherwise the exception handler will run all the time, which is not intended.
See here:

<img src="https://i.imgur.com/eE8yKKi.png"/>

### Main Flow
- **Purpose**: Retrieve all SharePoint sites using the Graph API.
- **Actions**:
  1. **Send an HTTP request**: Retrieves all SharePoint sites using Graph API.
  2. **Parse JSON**: Parses the response to make it easily accessible.
  3. **Select**: Extracts only the necessary details (currently weburl and displayName).
  4. **Respond to a PowerApp or flow**: Sends the extracted data back to a PowerApp or other flows.

### Exception Handler
- **Purpose**: Handles errors from the Main Flow.
- **Actions**:
  1. **Send an Email (V2)**: Notifies the exception receiver via email about the error.
  2. **Terminate**: Ends the flow if an error occurs.
  3. **Create HTML table**: Summarizes the errors in an HTML table.
  4. **Respond to a PowerApp or flow**: Sends an error response back to the initiator.

