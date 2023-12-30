



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
