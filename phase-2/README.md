
# Phase 2: Org Setup & Configuration

## 1. Salesforce Editions

The project is implemented on the **Salesforce Developer Edition org**, which provides free access for customization and testing.
For real-world deployment, **Enterprise Edition** would be recommended, as it supports advanced features like profiles, roles, sharing rules, API integration, and sandbox creation.



## 2. Company Profile Setup

Company profile set as **AR Clinic**.
Details such as company name, address
 primary contact, default currency (INR), and time zone were configured.
This ensures that all business processes in Salesforce reflect the clinic’s identity.

,<img width="1590" height="782" alt="Screenshot 2025-09-20 092604" src="https://github.com/user-attachments/assets/d2ee7293-463f-4a10-a66a-d1e60a8ba5ed" />


## 3. Business Hours & Holidays

Business hours configured as sunday(11:00 AM – 1:00 PM)**  and Monaday-Staurday(9:00AM - 6:00PM)to reflect clinic operating times.
Public holidays (e.g., **Diwali, Independence Day, New Year**) added to avoid scheduling appointments on non-working days.
<img width="1586" height="778" alt="Screenshot 2025-09-20 094719" src="https://github.com/user-attachments/assets/40c350ea-3cd5-42b1-9462-25c3490d3621" />

## 4. Fiscal Year Settings

Standard Fiscal Year chosen (**April–March**) to align with Indian financial standards.
This helps in generating accurate financial reports for clinic revenue and billing.


## 5. User Setup & Licenses

Users created for different roles: **Doctor, Receptionist, Admin**.
Each user assigned an appropriate Salesforce license:

* **Platform License** → Doctors and Receptionists.
* **Salesforce License** → Admin.

Profiles and permission sets used to define user access levels.
<img width="1557" height="743" alt="Screenshot 2025-09-20 095712" src="https://github.com/user-attachments/assets/f24b5433-8977-497e-b0d1-5364a33d3234" />

<img width="1566" height="765" alt="Screenshot 2025-09-20 095816" src="https://github.com/user-attachments/assets/6286609a-0c0d-4dc7-88c8-627fbbefd939" />

<img width="1543" height="768" alt="Screenshot 2025-09-20 095900" src="https://github.com/user-attachments/assets/89c87046-b346-4856-a8dd-2d44dfa6b7d8" />

## 6. Profiles

Profiles created to define baseline permissions:

* **Doctor Profile** – can manage patients and appointments.
* **Receptionist Profile** – can schedule appointments, handle billing, limited patient access.
* **Admin Profile** – full access to manage all data, users, and settings.

<img width="1572" height="492" alt="Screenshot 2025-09-20 100052" src="https://github.com/user-attachments/assets/102516c8-6ff4-4f26-8950-c6ef71a0ba33" />

<img width="1573" height="482" alt="Screenshot 2025-09-20 100152" src="https://github.com/user-attachments/assets/2dcc3d79-7ae6-4a4b-b382-35ecf993a7b6" />

## 7. Roles

Role hierarchy defined to control data visibility:

* **Clinic Admin** (top-level)

  * Doctor
  * Receptionist

Roles ensure that doctors only see their own patients/appointments and receptionists manage scheduling/billing without full data access.
<img width="1576" height="661" alt="Screenshot 2025-09-20 100524" src="https://github.com/user-attachments/assets/ed4b67dd-18d8-40bf-8a1c-3993053b9c26" />

<img width="1594" height="661" alt="Screenshot 2025-09-20 100745" src="https://github.com/user-attachments/assets/3e695b7f-a1c6-4bc2-9cf0-9cc496db443f" />

<img width="1557" height="680" alt="Screenshot 2025-09-20 100813" src="https://github.com/user-attachments/assets/ae395c39-be02-460e-bd08-5e1a0718527c" />


## 8. Custom Objects & Relationships

Custom objects created to manage clinic operations:

* **Patient** → Patient information and contact details.
* **Appointment** → Appointment details (Doctor, Patient, Date, Time, Status).
* **Billing** → Invoice and payment details.

Relationships established:

* Appointment → Patient (Lookup)
* Appointment → Doctor (Lookup)
* Billing → Patient (Lookup)
* Billing → Appointment (Lookup)
<img width="1886" height="742" alt="Screenshot 2025-09-20 101205" src="https://github.com/user-attachments/assets/3d6d236e-7f99-4a76-b7ed-74abaf4d9087" />


## 9. Permission Sets

A **Billing Access Permission Set** was created and assigned to Receptionists, giving them additional control over Billing records.


## 10. Reports & Dashboards

Basic reports and dashboards created to track:

* Patient visits per month
* Appointments by doctor
* Revenue from billing

<img width="1914" height="726" alt="Screenshot 2025-09-20 103923" src="https://github.com/user-attachments/assets/a12b6b91-cae6-4069-9573-2933a70e15c9" />

✅ With this configuration, **AR Clinic** now has a secure and structured Salesforce environment to manage patients, appointments, and billing effectively.
