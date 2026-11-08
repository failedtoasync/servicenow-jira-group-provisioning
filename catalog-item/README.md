# Catalog Item

The `Jira Group Provisioning Request` catalog item serves as the entry point for requesting new Jira groups through the Service Catalog. It allows users to submit requests for themselves or on behalf of another user, providing the group name and business justification required for processing.

After submission, ServiceNow creates a Requested Item (RITM) and triggers the `Jira Group Provisioning` flow, which manages the subsequent validation, approval, and provisioning process.

## Request Variables

The catalog item uses three mandatory variables to capture the information required for Jira group provisioning.

- **Requested For:** Identifies the user for whom the Jira group is being requested.
- **Jira Group Name:** Captures the name of the Jira group to be created. It is used for duplicate validation and group creation.
- **Business Justification:** Captures the reason for requesting the group and provides context for the approval process.

- ## Catalog Client Script

The `Default Request For` Catalog Client Script automatically populates the Requested For field with the currently logged-in user when the catalog item loads. The field remains editable, allowing users to submit requests on behalf of someone else.

**Script:** [default-request-for.js](default-request-for.js)
