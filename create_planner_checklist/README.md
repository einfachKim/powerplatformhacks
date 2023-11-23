# Power Automate Flow Documentation

## Overview
This Power Automate Flow is designed to automate tasks in SharePoint and Planner. It retrieves items from a SharePoint list, processes each item, creates tasks in Planner based on the SharePoint items, and updates task details accordingly, adding subtasks to the specific tasks.

## How to use?
Copy the json payload and insert it via STRG+V into your flow. Adjust all missing connections and choose your SharePoint List and Planner

## Flow Actions

### 1. Get Items from SharePoint
- **Description**: Retrieves items from a specified SharePoint list.

### 2. Apply to Each
- **Description**: Iterates over each item retrieved from the SharePoint list.
- **Actions within 'Apply to Each'**:
  - **Select**
  - **Compose**
  - **Create a Task in Planner**
  - **Update Task Details in Planner**

#### a. Select
- **Description**: Transforms `Sub_x002d_Task` from each SharePoint item into a specific format.
- **Inputs**: 
  - **From**: `Sub_x002d_Task` of the current item
  - **Map**: 
    - `id`: item's ID
    - `title`: item's value
    - `isChecked`: false

#### b. Compose
- **Description**: Composes the task and subtasks into a structured format.
- **Inputs**: 
  - `task`: Title of the SharePoint item
  - `subtasks`: Output from the Select action

#### c. Create a Task in Planner
- **Description**: Creates a new task in Planner based on the SharePoint item.
- **Parameters**:
  - `groupId`: Specific Group ID
  - `planId`: Specific Plan ID
  - `title`: Title of the SharePoint item

#### d. Update Task Details in Planner
- **Description**: Updates the details of the task created in Planner.
- **Parameters**:
  - `id`: ID of the created task
  - `checklist`: Checklist items extracted from the SharePoint item

## Additional Information
- **Connectors Used**:
  - Planner
  - Microsoft Forms
  - SharePoint Online


**Note**: The details provided above are based on the flow's JSON configuration. Adjustments may be required to align with actual implementation and usage scenarios.
