# Project Planning

## 1. Introduction

The project is planned to develop an automated IT ticket classification system for a school IT helpdesk using **ServiceNow Flow Designer**.

The planning process is divided into multiple phases, beginning with requirement analysis and continuing through configuration, automation, testing, validation, deployment, and final documentation.

## 2. Project Objectives

The main objectives of the project are:

* Automatically classify IT support tickets.
* Assign Category and Subcategory automatically.
* Reduce manual effort for IT staff.
* Improve ticket routing efficiency.
* Maintain structured and standardized ticket information.
* Send automated email notifications to callers.
* Build a maintainable and scalable no-code solution.

## 3. Project Phases

The project is planned using the following major phases:

| Phase   | Major Activities                    | Expected Output                    |
| ------- | ----------------------------------- | ---------------------------------- |
| Phase 1 | Requirement Analysis & Planning     | Business and system requirements   |
| Phase 2 | Backend Development & Configuration | Custom ticket table and fields     |
| Phase 3 | Flow Designer Automation            | Automatic ticket classification    |
| Phase 4 | Testing, Validation & Security      | Verified and validated system      |
| Phase 5 | Deployment & Final Documentation    | Deployable and documented solution |

## 4. Phase 1 – Requirement Analysis & Planning

The first phase focuses on understanding the existing helpdesk process and identifying the problems with manual ticket classification.

### Activities

* Identify common IT support issues.
* Analyze the existing manual classification process.
* Define business requirements.
* Identify required ticket fields.
* Define Category and Subcategory values.
* Define the automation requirements.
* Plan email notification requirements.

The main requirement is to automatically classify tickets based on the issue description and assign the appropriate Category and Subcategory.

## 5. Phase 2 – Backend Development & Configuration

The second phase focuses on creating and configuring the data structure required for the project.

### Activities

* Create the **Incident Workflow** custom table.
* Configure Auto Number for ticket identification.
* Create required ticket fields.
* Configure field data types.
* Add Category choices.
* Add Subcategory choices.
* Add State choices.
* Configure the dependency between Category and Subcategory.

The project defines fields such as Caller, Category, Subcategory, Short Description, Description, State, Assigned Group, and Assigned To.

## 6. Phase 3 – Automation Development

The third phase focuses on implementing automatic ticket classification using **Flow Designer**.

### Planned Flow

```text
New Ticket Created
        |
        v
Check Category
        |
        v
Read Short Description
        |
        v
Identify Keywords
        |
        +-------------------+
        |                   |
        v                   v
  Matching Issue       No Matching Issue
        |
        v
Assign Category
        |
        v
Assign Subcategory
        |
        v
Send Email Notification
```

The documented flow uses a **Record Created** trigger and checks whether the Category field is empty before performing classification.

### Classification Plan

| Detected Issue   | Category    | Subcategory     |
| ---------------- | ----------- | --------------- |
| WiFi / Network   | Network     | Wi-Fi           |
| Projector        | Hardware    | Projector       |
| Password / Login | Access      | Forgot Password |
| Slow / Hanging   | Performance | Slow Computer   |

These rules are implemented using conditional branches and Update Record actions in Flow Designer.

## 7. Phase 4 – Testing, Validation & Security

The fourth phase focuses on verifying that the complete automation works correctly.

### Testing Activities

* Create test tickets.
* Test Wi-Fi classification.
* Test Projector classification.
* Test Password classification.
* Test Slow Computer classification.
* Verify Category values.
* Verify Subcategory values.
* Verify email notifications.
* Check auto-number generation.
* Validate reference fields.
* Verify data accuracy.

For example, a ticket with the Short Description **"WiFi not working in library"** should be classified as:

```text
Category    → Network
Subcategory → WiFi
```

and an email should be sent to the caller.

## 8. Phase 5 – Deployment & Final Documentation

The final phase prepares the project for deployment and future reuse.

### Activities

* Complete final testing.
* Verify the project configuration.
* Change the Update Set state from **In Progress** to **Complete**.
* Export the Update Set as XML.
* Prepare final project documentation.
* Prepare the solution for demonstration or deployment.

The project documentation specifies exporting the completed Update Set to XML for sharing and transferring the configuration.

## 9. Project Workflow

The complete planned workflow is:

```text
Requirement Analysis
        ↓
Database & Field Design
        ↓
Category/Subcategory Configuration
        ↓
Flow Designer Development
        ↓
Keyword-Based Classification
        ↓
Email Notification
        ↓
Testing & Validation
        ↓
Security Validation
        ↓
Deployment
        ↓
Final Documentation
```

## 10. Expected Deliverables

At the completion of the project, the following deliverables are expected:

* Configured Incident Workflow table.
* Required ticket fields.
* Category and Subcategory dependency.
* Auto Ticket Classification Flow.
* Automated email notification.
* Tested ticket classification scenarios.
* Completed Update Set.
* Exported XML configuration.
* Final project documentation.

## 11. Future Planning

The solution can be extended in future development stages with additional automation features such as:

* Automatic assignment of tickets.
* SLA tracking.
* Additional ticket categories.
* Predictive intelligence.
* Advanced ticket management features.

The project documentation identifies assignment automation, SLA tracking, and predictive intelligence as possible future extensions.

## 12. Conclusion

The project planning provides a structured path from identifying the helpdesk problem to developing, testing, and deploying an automated ticket classification solution. The phased approach helps organize the development activities and ensures that the final ServiceNow solution is maintainable, scalable, and ready for demonstration or deployment.
