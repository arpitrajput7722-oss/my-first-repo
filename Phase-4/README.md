# Phase 4 — Process Automation (Clinic Management System) — Description with Screenshots

## Objective

Automate core processes in the Clinic Management System for data integrity, patient communication, and financial governance.

### Step 1: Validation Rule

* A validation rule is applied on the Appointment object to prevent users from scheduling appointments in the past. This ensures data accuracy and prevents errors.
<img width="1742" height="607" alt="Screenshot 2025-09-24 214702" src="https://github.com/user-attachments/assets/6c242529-9161-4a44-98a4-17c315106800" />

-

### Step 2: Record-Triggered Flow

* When an Appointment status is updated to 'Completed', the Flow automatically sets `Visited__c = TRUE` and calculates the `Follow_Up_Date__c` to be 30 days after the appointment. This automates the follow-up scheduling.

<img width="1908" height="913" alt="Screenshot 2025-09-25 141842" src="https://github.com/user-attachments/assets/b72655e9-8c43-4f0d-b48a-52760a2a49e8" />



### Step 3: Scheduled Flow (Reminder Email)

* When a new Appointment is created, a scheduled flow sends a reminder email to the patient one day before the appointment date using the pre-created email template. This ensures timely communication with patients.


### Step 4: Approval Process (Billing/Invoice)

**Description:** For the Billing object, if the Amount exceeds 5000, the record is sent automatically to the Admin for approval. An assignment email template notifies the approver. This enforces financial control.
<img width="1878" height="827" alt="Screenshot 2025-09-25 142035" src="https://github.com/user-attachments/assets/b03ea896-1e61-4cf8-85cd-96516be7759b" />

