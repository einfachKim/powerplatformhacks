## Power Automate Cloud Flow Documentation

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

