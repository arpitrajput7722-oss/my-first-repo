# 📄 Phase 3: Object & Data Model Setup (Clinic Project)

## 1️⃣ Create Custom Objects

In this step, new custom objects were created to represent the core entities of the clinic system that are not available as standard Salesforce objects.

* **Patient** – To capture details of each patient visiting the clinic.
* **Appointment** – To manage scheduled visits between patients and doctors.
* **Invoice** – To record billing and payment transactions for appointments.

These objects provide the foundation of the Clinic Management System and are visible in the Object Manager.


## 2️⃣ Add Essential Fields

Each custom object was enhanced with important fields to capture relevant information:

**Patient**

* *Date of Birth (Date):* To record patient age details.
* *Gender (Picklist):* Options – Male, Female, Other.
* *Phone (Phone):* Primary contact number of the patient.
* *Medical History (Long Text):* Notes on previous conditions or allergies.
* <img width="1909" height="693" alt="Screenshot 2025-09-23 195545" src="https://github.com/user-attachments/assets/dedd07a6-5a67-497d-9d25-5cc08ecb1c27" />


**Appointment**

* *Patient (Lookup → Patient):* To link the appointment with the patient record.
* *Doctor (Lookup → User):* To assign the doctor responsible for the appointment.
* *Appointment Date (Date/Time):* The scheduled date and time of the visit.
* *Status (Picklist):* Options – Scheduled, Completed, Cancelled.
* *Reason (Text/Long Text):* Notes on the purpose of the visit.
<img width="1900" height="794" alt="Screenshot 2025-09-23 195612" src="https://github.com/user-attachments/assets/866efb9e-51a4-4f1d-a176-e714ac53a0f2" />

**Invoice**

* *Appointment (Lookup → Appointment):* To tie the invoice to a specific appointment.
* *Patient (Lookup → Patient):* For direct patient reference.
* *Amount (Currency):* Total charge for the treatment or consultation.
* *Payment Status (Picklist):* Options – Paid, Pending, Partial.
* *Payment Date (Date):* Date on which payment was made.
<img width="1884" height="740" alt="Screenshot 2025-09-23 195642" src="https://github.com/user-attachments/assets/ec626fe6-4ace-4819-b541-fe8f6741a695" />


## 3️⃣ Create Relationships

Relationships were set up to connect the custom objects with each other and with standard objects:

* **Appointment → Patient (Lookup Relationship):** Links every appointment to a registered patient.
* **Appointment → Doctor (Lookup → User):** Associates the appointment with the doctor handling it.
* **Invoice → Appointment (Lookup Relationship):** Ensures that billing records are tied to appointments.
* **Invoice → Patient (Lookup Relationship):** Provides direct visibility into the patient’s billing history.

These relationships ensure that all data is connected, making it easier to generate reports and dashboards.


## 4️⃣ Page Layouts

Page layouts were customized to improve usability and ensure that the most important fields are visible during record creation or editing:

* **Patient Layout:** Shows patient demographics (DOB, Gender, Phone) and displays related appointments.
* **Appointment Layout:** Displays patient lookup, doctor assignment, appointment date/time, and status.
* **Invoice Layout:** Includes fields for patient, appointment, amount, payment status, and payment date.

This customization ensures that end users such as receptionists and doctors can quickly enter and retrieve information.
<img width="1894" height="644" alt="Screenshot 2025-09-23 201115" src="https://github.com/user-attachments/assets/bb860f2b-3bc4-48fc-b0f4-d7cc4668497c" />
<img width="1905" height="340" alt="Screenshot 2025-09-23 201225" src="https://github.com/user-attachments/assets/2540cb8b-fed1-4835-824d-9f0582319ca4" />
<img width="1893" height="510" alt="Screenshot 2025-09-23 201305" src="https://github.com/user-attachments/assets/fd04ef47-6d58-4417-9793-62babbddf6cc" />


## 5️⃣ Create Sample Records

Sample records were created to test the system and verify that relationships are working correctly:

* **Patient:** Rakesh Kumar(Male, 35 years, Phone: +91-9876543210).
* **Doctor (User):** Dr. Rajpoot (created as a Salesforce user).
* **Appointment:** Rakesh Kumar booked with Dr. Rajpoot on *25 Sept*, Status: Scheduled.
* **Invoice:** Linked to the appointment, with an amount of ₹1000, Status: Pending.

These records confirm that data is flowing correctly between Patient, Appointment, and Invoice objects.

<img width="1919" height="502" alt="Screenshot 2025-09-23 183856" src="https://github.com/user-attachments/assets/1f2d42e6-524d-4969-906c-f47d86e3c199" />


## 6️⃣ Schema Builder

The **Salesforce Schema Builder** was used to visually map and confirm the data model. It clearly shows how the custom objects are connected to each other through lookup relationships.

* Patient connected to Appointment.
* Appointment connected to Doctor (User).
* Invoice connected to Appointment and Patient.

This visual representation validates the design and can be used for documentation and presentations.
<img width="1128" height="778" alt="Screenshot 2025-09-23 182839" src="https://github.com/user-attachments/assets/3906ba92-2f9a-4611-8193-f4468c7280ed" />
<img width="1903" height="792" alt="Screenshot 2025-09-23 182802" src="https://github.com/user-attachments/assets/75ce248f-4e08-4c8b-9ecf-d53755e4a030" />



✅ With these steps, the **data model for AR Clinic** is fully established. Patients, doctors, appointments, and billing are now logically connected, making it easier to extend the project with automation, reports, and dashboards in the next phase.

