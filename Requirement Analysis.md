# Requirement Analysis

## 1. Introduction

The school IT helpdesk receives multiple support requests every day from students and teachers. These requests commonly involve network connectivity, hardware failures, account access problems, and system performance issues.

Currently, IT staff manually review each ticket, identify the issue type, select the appropriate category and subcategory, and inform the caller about ticket creation. This manual process is time-consuming, error-prone, and difficult to scale as the number of requests increases.

The proposed system automates the ticket classification process using **ServiceNow Flow Designer**. The system analyzes the issue description and automatically assigns the appropriate Category and Subcategory.

## 2. Business Requirements

The system must satisfy the following business requirements:

1. Automatically classify IT tickets based on the issue description.
2. Assign both **Category** and **Subcategory** without manual intervention.
3. Support dependent-choice logic between Category and Subcategory.
4. Send an automated email notification to the caller after ticket creation.
5. Store ticket information in a structured and standardized format.
6. Ensure easy maintenance and future scalability.

## 3. Functional Requirements

### 3.1 Automatic Ticket Classification

The system should automatically identify the type of IT issue from the ticket description.

The classification should support common issues such as:

* Wi-Fi problems
* Projector problems
* Password or login problems
* Slow or hanging computers

### 3.2 Category Assignment

Based on the identified issue, the system should automatically assign a suitable category:

| Issue                   | Category    |
| ----------------------- | ----------- |
| Wi-Fi / Network         | Network     |
| Projector               | Hardware    |
| Password / Login        | Access      |
| Slow / Hanging Computer | Performance |

### 3.3 Subcategory Assignment

The system should automatically assign the corresponding subcategory:

| Category    | Subcategory     |
| ----------- | --------------- |
| Network     | Wi-Fi           |
| Hardware    | Projector       |
| Access      | Forgot Password |
| Performance | Slow Computer   |

The project uses dependent-choice logic so that the available subcategory options depend on the selected category.

### 3.4 Email Notification

After a ticket is created and processed, an automated email should be sent to the caller's email address confirming ticket creation.

### 3.5 Structured Data Storage

Ticket information should be stored using appropriate fields and data types, including:

* Number
* Caller
* Category
* Subcategory
* Short Description
* Description
* State
* Assigned Group
* Assigned To

The project defines these fields as part of the ticket table configuration.

## 4. Non-Functional Requirements

### 4.1 Maintainability

The solution should be easy to maintain. The project uses Flow Designer and a no-code approach so that the automation can be modified without relying on complex scripting.

### 4.2 Scalability

The system should allow additional ticket categories, subcategories, and classification conditions to be added in the future.

### 4.3 Data Accuracy

Category and Subcategory values should be stored accurately, and dependent-choice logic should help maintain consistent data.

### 4.4 Usability

Students and teachers should be able to create support tickets without manually selecting the Category or Subcategory. The automation performs the classification after ticket submission.

### 4.5 Reliability

The system should consistently classify supported ticket types and send the required email notification.

## 5. Data Requirements

The ticket record requires the following fields:

| Field             | Type                         |
| ----------------- | ---------------------------- |
| Number            | Auto Number                  |
| Caller            | Reference — `sys_user`       |
| Category          | Choice                       |
| Subcategory       | Choice                       |
| Short Description | String                       |
| Description       | String                       |
| State             | Choice                       |
| Assigned Group    | Reference — `sys_user_group` |
| Assigned To       | Reference — `sys_user`       |

The defined Category choices are **Network, Hardware, Access, and Performance**, while the State choices include **New, In Progress, On Hold, Resolved, and Closed**.
