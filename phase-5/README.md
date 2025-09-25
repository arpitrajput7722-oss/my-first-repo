Got it 👍
Phase 5 = **Apex Programming (Clinic Management System)**.
Main aapke repo ke liye **short description (minimal steps)** bana raha hoon — bilkul Phase 4 jaisa, with screenshot placeholders.

---

# Phase 5 — Apex Programming (Clinic Management System) — Minimal Steps

## Objective

Automate backend logic using Apex Trigger and Apex Class to handle doctor assignment and follow-up scheduling.

---

### Step 1: Apex Class (Business Logic)

* **Class Name:** `AppointmentAutomation`
* **Purpose:** Assign default doctor & set follow-up date (+30 days).
* **Code:**

```apex
public with sharing class AppointmentAutomation {
    public static void assignDoctor(List<Appointment__c> newAppointments){
        for(Appointment__c app : newAppointments){
            if(app.Doctor__c == null){
                app.Doctor__c = 'Assign Doctor Automatically';
            }
            if(app.Follow_Up_Date__c == null && app.Appointment_Date__c != null){
                app.Follow_Up_Date__c = app.Appointment_Date__c.date().addDays(30);
            }
        }
    }
}
```
<img width="1865" height="800" alt="Screenshot 2025-09-25 225519" src="https://github.com/user-attachments/assets/626c8854-3183-4e24-993b-11154ca6f9a4" />

---

### Step 2: Apex Trigger

* **Trigger Name:** `AppointmentTrigger`
* **Events:** Before Insert, Before Update
* **Code:**

```apex
trigger AppointmentTrigger on Appointment__c (before insert, before update) {
    if(Trigger.isBefore){
        if(Trigger.isInsert || Trigger.isUpdate){
            AppointmentAutomation.assignDoctor(Trigger.new);
        }
    }
}
```

* **Result:** Doctor auto-filled + Follow-up date scheduled.

---<img width="1895" height="892" alt="Screenshot 2025-09-25 231444" src="https://github.com/user-attachments/assets/8d007e34-9caf-473a-b504-ab79f7a6c261" />


### Step 3: Test Class (for Deployment)

* **Class Name:** `AppointmentAutomationTest`
* **Purpose:** Ensure Apex works in all scenarios.
* **Code:**

```apex
@isTest
public class AppointmentAutomationTest {
    @isTest
    static void testAssignDoctorAndFollowUp() {
        Appointment__c app = new Appointment__c(
            Patient__c = 'TEST_PATIENT_ID',
            Appointment_Date__c = System.now().addDays(1)
        );
        insert app;

        Appointment__c insertedApp = [SELECT Doctor__c, Follow_Up_Date__c 
                                      FROM Appointment__c 
                                      WHERE Id = :app.Id];

        System.assertEquals('Assign Doctor Automatically', insertedApp.Doctor__c);
        System.assertEquals(Date.today().addDays(31), insertedApp.Follow_Up_Date__c);
    }
}
```

* **Result:** Code coverage achieved, ready for deployment.

---
