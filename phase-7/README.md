# Phase 7 — Integration & External Access (Clinic Management System)

## Objective

Enable **external access** and integrate the Clinic Management System with outside systems for smooth data sharing.

---

### Step 1: Enable API Access

* Salesforce API access enabled for Clinic Management objects (Patient, Appointment, Billing).
* Ensures data can be read/written externally<img width="1344" height="766" alt="Screenshot 2025-09-26 160141" src="https://github.com/user-attachments/assets/58e07a50-f5e1-49a8-8775-18aec121fad9" />
.

---

### Step 2: Create Connected App

* A **Connected App** was created for external system login.
* Configured with OAuth and callback URL for secure access.

<img width="1873" height="838" alt="Screenshot 2025-09-26 160635" src="https://github.com/user-attachments/assets/d59990d2-da9e-44d0-a956-d35e3bf341b8" />

### Step 3: Generate API Credentials

* Consumer Key & Secret generated for integration.
* Used by external apps (Postman/third-party system) to authenticate.
`
<img width="1521" height="795" alt="Screenshot 2025-09-26 155833" src="https://github.com/user-attachments/assets/f1a4830d-5874-4e83-8450-5860a9b966e4" />

---

### Step 4: External Data Access Test

* API tested using **Postman** (SOQL query for Patients & Appointments).
* Verified that external system can fetch/update clinic data.


## ✅ Outcome

* Clinic Management System is now accessible externally.
* External apps can authenticate via Connected App and perform operations.
* This phase ensures **secure integration & external connectivity**.
