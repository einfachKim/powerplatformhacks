### Flow documentaion

#### Main Flow (ID: 6220c582-319e-433e-8466-69ea536d8ed5)
Retrieves all views from a specified SharePoint list and filters to provide essential details such as Title, DefaultView, and ViewFieldsUri. It ends by responding back with the selected information.


#### Exception Handler (ID: b8af0d7b-da37-4e2a-ab0e-3ee963c0004b)
Handles any errors from the main flow by sending a detailed email to the designated receiver and terminating the flow if any exception is encountered. It ensures users are notified of any issues in the process.
