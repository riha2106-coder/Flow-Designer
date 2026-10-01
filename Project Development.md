# Project Development

## 1. Introduction

The development of the **Auto Ticket Classification using Flow Designer** project is carried out in ServiceNow using a phased approach. The implementation includes backend table configuration, field creation, dependent choice configuration, Flow Designer automation, email notification, testing, and deployment.

The main purpose of development is to automate the classification of school IT support tickets based on keywords present in the Short Description.

## 2. Development Environment

The project is developed using **ServiceNow** and its **Flow Designer** platform.

The solution uses a no-code approach to implement the ticket classification logic and email notification.

## 3. Custom Table Development

A custom table named **Incident Workflow** is created to store the ticket records.

### Steps

1. Open **All → System Definition → Tables**.
2. Click the **New** button.
3. Set the table label as **Incident Workflow**.
4. Disable the **Create module** option.
5. Save the form.
6. Open the **Controls** section.
7. Enable **Auto Number**.
8. Save the form again.

The Auto Number feature provides a structured ticket number for each record.

## 4. Field Development

The required fields are created in the Incident Workflow table.

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

These fields provide the required structure for storing and processing IT support tickets.

## 5. Choice Configuration

Choice values are added to the appropriate fields.

### Category

The Category field contains:

* Network
* Hardware
* Access
* Performance

### Subcategory

The Subcategory field contains:

* Wi-Fi
* Projector
* Forgot Password
* Slow Computer

### State

The State field contains:

* New
* In Progress
* On Hold
* Resolved
* Closed

The project uses choice fields to maintain standardized ticket information.

## 6. Category and Subcategory Dependency

A dependency is created between the **Category** and **Subcategory** fields.

### Configuration Steps

1. Open the Incident Workflow form.
2. Right-click the **Subcategory** field.
3. Select **Configure Dictionary**.
4. Open **Advanced view**.
5. Enable **Use dependent field**.
6. Select **Category** as the dependent field.
7. Save the configuration.

The following dependency mapping is configured:

| Subcategory     | Category    |
| --------------- | ----------- |
| Wi-Fi           | Network     |
| Projector       | Hardware    |
| Forgot Password | Access      |
| Slow Computer   | Performance |

This ensures that the Subcategory choices are displayed according to the selected Category.

## 7. Flow Designer Development

The main automation is developed using **ServiceNow Flow Designer**.

### Flow Creation

1. Open **All → Process Automation → Flow**
