# ServiceNow–Jira Group Provisioning

A ServiceNow catalog-based solution that streamlines Jira group provisioning through standardized requests, duplicate validation, approval-driven automation, and Jira Spoke integration. The solution also includes automated notifications, request lifecycle tracking, and a support process for handling provisioning failures.

## Technical Stack & Capabilities

The solution uses ServiceNow catalog capabilities, workflow automation, and Jira Spoke integration to manage group provisioning.

- **Service Catalog:** Catalog item design and request variables.
- **Catalog Client Scripts:** Default Requested For field value.
- **Flow Designer:** Group validation, approvals, provisioning, notifications, and request management.
- **IntegrationHub & Jira Spoke:** Jira group lookup and creation.
- **Requested Items & Catalog Tasks:** Request tracking and support intervention.

## Table of Contents

1. [Business Context & Solution](#1-business-context--solution)
2. [System Architecture & Workflow](#2-system-architecture--workflow)
   - [Jira Group Provisioning Request](#jira-group-provisioning-request)
   - [Group Validation & Approval](#group-validation--approval)
   - [Jira Group Creation & Exception Handling](#jira-group-creation--exception-handling)
   - [Request Lifecycle & Notifications](#request-lifecycle--notifications)
   - [Integration & Access Security](#integration--access-security)
3. [Testing & Verification](#3-testing--verification)
4. [Repository File Index](#4-repository-file-index)

---

## 1. Business Context & Solution

Creating Jira groups often requires coordination with Jira administrators to verify existing groups, obtain approval, and complete provisioning. Without a structured request process, tracking requests and handling provisioning issues can become difficult.

**Jira Group Provisioning** provides a centralized Service Catalog process for requesting new Jira groups. Flow Designer validates group availability, manages approval, and uses Jira Spoke to automate group creation, with a defined process for handling provisioning failures.

## 2. System Architecture & Workflow

### Jira Group Provisioning Request

The `Jira Group Provisioning Request` catalog item provides a standardized entry point for users to request new Jira groups. It establishes a consistent request process within ServiceNow and captures the information needed for provisioning.

### Group Validation & Approval

The `Jira Group Provisioning` flow incorporates duplicate group validation and approval controls into the provisioning process. This helps prevent duplicate group creation and ensures requests are reviewed before provisioning proceeds.

### Jira Group Creation & Exception Handling

Jira Spoke integration enables automated group creation in Jira following approval. For cases where automated provisioning cannot be completed, a Catalog Task provides a structured path for support review and manual intervention.

### Request Lifecycle & Notifications

The solution uses Requested Item (RITM) states to track each request from submission through its final outcome, providing visibility into approval, provisioning, and support activities. Automated notifications keep requesters informed of important decisions and fulfillment outcomes.

### Integration & Access Security

The solution connects ServiceNow with Jira through the Jira Spoke integration. Access to ServiceNow catalog and fulfillment records is governed by the platform's security and access controls.

## 3. Testing & Verification

Testing covers the main provisioning scenarios, including successful group creation, duplicate detection, approval rejection, Jira creation failures, and support intervention outcomes.

Detailed test scenarios and supporting screenshots are documented in [Testing and Evidence](testing-and-evidence/README.md).

## 4. Repository File Index

- [**Catalog Item**](catalog-item/) — Catalog item configuration, request variables, and client scripting.
- [**Flow Designer**](flow-designer/) — Jira Spoke integration, provisioning workflow, and exception handling.
- [**Testing**](testing/) — Test scenarios and supporting screenshots.
