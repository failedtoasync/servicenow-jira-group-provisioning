# Flow Designer

The `Jira Group Provisioning` flow manages the fulfillment of Jira group creation requests submitted through the Service Catalog. It coordinates group validation, approval, and automated provisioning through Jira Spoke, while managing request outcomes and handling technical failures that require support intervention.

## Jira Spoke Integration Setup

The integration uses Jira Spoke to perform group lookup and creation in Jira. A dedicated Connection and Credential Alias, HTTP connection, and credential were configured to establish the connection with Jira Cloud.

### Request Trigger & Variable Retrieval 

The flow uses a Service Catalog trigger. When a request is submitted, the flow retrieves the submitted catalog variables using the **Get Catalog Variables** action, making the request information available for subsequent validation, approval, and provisioning steps.

### Group Lookup & Duplicate Validation

The flow uses the `Look Up Groups Stream` Jira Spoke action to retrieve existing Jira groups. A `For Each` loop processes the returned group collection and compares group names against the requested group name.

If a matching group is found, the request is marked as Closed Incomplete and the requester is notified. The approval and group creation steps are skipped. If no match is found, the request proceeds to approval.

### Approval & Jira Group Creation

When no existing group is found, the request moves to the Pending state and proceeds for approval. If approval is rejected, the request is marked as Closed Incomplete and the requester is notified.

For approved requests, the RITM moves to Work in Progress, and the flow uses the `Create Group` Jira Spoke action to create the requested group in Jira. Upon successful creation, the RITM is marked as Closed Complete and the requester receives a notification.

### Technical Failure & Support Intervention

If Jira group creation cannot be completed automatically, the request remains in Work in Progress and enters the Support Review stage. The flow creates a Catalog Task for manual support intervention. Based on the support task outcome, the RITM is marked as Closed Complete or Closed Incomplete, and the requester is notified.

## Notifications

The flow includes automated notifications to keep requesters and approvers informed of request progress, approval decisions, and provisioning outcomes.

