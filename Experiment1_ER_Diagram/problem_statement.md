# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Student Name

## Scenario Chosen:
 Hospital 

## ER Diagram:
![Screenshot (64)](https://github.com/user-attachments/assets/aa9c46b8-f32a-4a4d-91d2-a85fcebdc0dc)


## Entities and Attributes:
Patient
Attributes: Patient_id, Patient_name, DOB, Gender, Address
Appointment
Attributes: Token_no, Time
Doctor
Attributes: Doctor_id, Doctor_name, Phone_no
Treatment
Attributes: Diagnosis, Medicine, Test_result

## Relationships and Constraints:

Books (between Patient and Appointment)
Cardinality: One patient can book many appointments; one appointment is booked by one patient.
Participation: Total on the side of Appointment (every appointment must be booked), partial on the side of Patient.
Conducted_by (between Appointment and Doctor)
Cardinality: One doctor can conduct many appointments; each appointment is conducted by one doctor.
Participation: Total on the side of Appointment.
Visit (between Doctor and Treatment)
Cardinality: A doctor can provide many treatments; each treatment is linked to one doctor.
Participation: Partial on both ends.

## Extension (Prerequisite / Billing):

There is no direct billing or prerequisite relationship modeled in this ER diagram. However, a billing extension could be introduced as:
A new Billing entity connected to Treatment, with attributes like Bill_id, Amount, Payment_status, and Date.
A Requires relationship could be added if modeling prerequisites (e.g., a patient must have a prior test result or referral).

## Design Choices:

Entity Selection: Entities are chosen based on real-world hospital components — patients, appointments, doctors, and treatments.
Attributes: Core identifying and descriptive information is included for each entity (e.g., IDs, names, contact details).
Relationships: The diagram emphasizes the patient journey — from booking an appointment to receiving treatment.
Assumptions:
Each appointment is linked to exactly one patient and one doctor.
Each treatment is associated with one visit by a doctor.
There is no many-to-many mapping shown between treatments and patients directly — it's inferred via appointments and doctors.


## RESULT

The ER diagram successfully models a basic hospital management system focusing on patient appointments and treatments. It includes the core entities—Patient, Doctor, Appointment, and Treatment—with appropriate attributes and relationships:
Patients can book appointments, which are conducted by doctors.
Doctors provide treatments during visits, and each treatment includes diagnosis, medicine, and test results.
The relationships are logically structured to maintain referential integrity and capture the workflow from appointment to treatment.
This ER model can serve as the foundational design for implementing a relational database system in a hospital environment, ensuring efficient handling of patient-doctor interactions and treatment records.
