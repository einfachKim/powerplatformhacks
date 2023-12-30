### SharePoint List Deletion Flow Documentation

#### Purpose
This flow is designed to delete a specific SharePoint list based on given parameters.

#### Actions
1. **Send HTTP Request to SharePoint**: Executes a DELETE request to remove a specified SharePoint list using its unique identifier.
2. **Respond to PowerApp or Flow**: Sends a status message back to the PowerApp or flow to confirm the action's success or failure.

The exception handler provides a robust error management mechanism, sending email alerts for failures and logging detailed information for troubleshooting purposes.
