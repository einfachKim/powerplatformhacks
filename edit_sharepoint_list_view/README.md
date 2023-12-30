### Power Automate Cloud Flow Documentation


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
