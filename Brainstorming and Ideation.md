# Brainstorming and Ideation

## 1. Problem Identification

The school IT helpdesk receives multiple incident requests every day from students and teachers. Common issues include:

* Wi-Fi or network connectivity problems
* Projector failures
* Password and login problems
* Slow or hanging computers

Currently, IT staff manually review each ticket and select the appropriate category and subcategory. This process is time-consuming, error-prone, and difficult to scale as the number of support requests increases.

## 2. Brainstorming Ideas

During the brainstorming stage, several possible approaches were considered to improve the ticket classification process:

### Idea 1: Manual Ticket Classification

IT staff manually review every ticket and select the appropriate category and subcategory.

**Limitation:**
This requires additional effort from IT staff and may result in inconsistent classification.

### Idea 2: Keyword-Based Automatic Classification

The system can analyze the ticket's short description and identify predefined keywords such as:

* `WiFi`
* `Network`
* `Projector`
* `Password`
* `Login`
* `Slow`
* `Hanging`

Based on the detected keyword, the system can automatically assign the corresponding category and subcategory.

### Idea 3: Automated Email Notification

After a ticket is created and classified, the system can automatically send an email confirmation to the caller.

This provides immediate confirmation that the support request has been successfully submitted.

### Idea 4: Dependent Category and Subcategory

The Category and Subcategory fields can be connected using dependent-choice logic.

For example:

| Category    | Subcategory     |
| ----------- | --------------- |
| Network     | Wi-Fi           |
| Hardware    | Projector       |
| Access      | Forgot Password |
| Performance | Slow Computer   |

This prevents unrelated subcategory options from being selected.

### Idea 5: No-Code Automation

Instead of using complex scripting or machine learning, ServiceNow **Flow Designer** can be used to implement the automation.

The flow can:

1. Detect the creation of a new ticket.
2. Check whether the Category field is empty.
3. Analyze the Short Description.
4. Identify predefined keywords.
5. Assign the appropriate Category.
6. Assign the appropriate Subcategory.
7. Send an email notification to the caller.

## 3. Selected Idea

The selected approach is **Auto Ticket Classification using ServiceNow Flow Designer**.

The solution uses predefined keyword conditions to classify common school IT support tickets automatically. This approach is intended to reduce manual classification effort while keeping the implementation simple and maintainable.

## 4. Classification Logic

The proposed classification logic is:

| Keyword/Issue    | Category    | Subcategory     |
| ---------------- | ----------- | --------------- |
| WiFi / Network   | Network     | Wi-Fi           |
| Projector        | Hardware    | Projector       |
| Password / Login | Access      | Forgot Password |
| Slow / Hanging   | Performance | Slow Computer   |

The Flow Designer uses conditional logic to identify these issues and update the ticket accordingly.

## 5. Expected Benefits

The proposed idea is expected to provide the following benefits:

* Reduce manual work for IT staff.
* Automatically classify tickets during creation.
* Improve consistency in ticket categorization.
* Reduce classification errors.
* Improve ticket routing efficiency.
* Provide automatic confirmation to callers through email.
* Maintain structured ticket information.
* Provide a no-code solution that is easier to maintain.
* Allow the system to be extended with additional automation features.

## 6. Future Ideation

The project can be extended in the future with additional features such as:

* Automatic assignment to IT support groups.
* SLA tracking.
* More ticket categories and subcategories.
* Additional keyword patterns.
* Predictive intelligence.
* Automated ticket prioritization.
* Advanced reporting and dashboards.

## 7. Final Ideation

The final concept is to create a **simple, no-code, automated IT ticket classification system** using ServiceNow Flow Designer. The system analyzes the short description entered by the student or teacher, identifies the issue type, automatically assigns the appropriate Category and Subcategory, and sends an email confirmation to the caller.

This provides an organized approach for handling common school IT support requests and creates a foundation for future automation.
