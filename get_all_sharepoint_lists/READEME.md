## Power Automate Cloud Flow Documentation

### How to use?


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
