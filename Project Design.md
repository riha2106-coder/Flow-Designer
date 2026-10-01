# Project Design

## 1. Introduction

The project is designed to automate the classification of school IT support tickets using **ServiceNow Flow Designer**. The design focuses on automatically identifying common IT issues from the ticket's Short Description and assigning the appropriate Category and Subcategory.

The solution follows a structured, no-code architecture consisting of ticket storage, dependent choice fields, Flow Designer automation, and email notification.

## 2. System Architecture

The overall project design can be represented as follows:

```text
Student / Teacher
       |
       v
Create IT Support Ticket
       |
       v
Incident Workflow Table
       |
       v
Flow Designer Trigger
       |
       v
Read Short Description
       |
       v
Keyword-Based Classification
       |
       +------------------+------------------+------------------+
       |                  |                  |                  |
       v                  v                  v                  v
     Wi-Fi            Projector          Password          Slow Computer
       |                  |                  |                  |
       v                  v                  v                  v
   Network            Hardware           Access          Performance
       |                  |                  |                  |
       +------------------+------------------+------------------+
                              |
                              v
                    Update Ticket Record
                              |
                              v
                    Send Email Notification
```

## 3. Database / Table Design

A custom table named **Incident Workflow** is created to store the ticket records.

The table uses an **Auto Number** configuration for generating ticket numbers.

### Ticket Fields

| Field  | Data Type   | Purpose                      |
| ------ | ----------- | ---------------------------- |
| Number | Auto Number | Unique ticket identification |
| Caller |             |                              |
