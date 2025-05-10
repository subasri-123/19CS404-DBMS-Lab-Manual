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

# ER Diagram Submission - Subasri B

## Scenario Chosen:
Hospital

## ER Diagram:

![image](https://github.com/user-attachments/assets/830e72b6-55e2-402a-bce7-591aefd207d9)

## Entities and Attributes:
Patient
Attributes: Patient_id, Patient_name, DOB, Gender, Address

Appointment
Attributes: Token_no, Time

Doctor
Attributes: Doctor_id, Doctor_name, Phone_no

Treatment
Attributes: Diagnos, Medicine, Test_result

## Relationships and Constraints:
Books Between: Patient and Appointment
Cardinality & Participation: Not explicitly mentioned (assumed many-to-many or one-to-many)

Conducted by Between: Doctor and Appointment
Cardinality & Participation: Not specified (likely one-to-many from diagram flow)

Visit Between: Appointment and Treatment
Cardinality & Participation: Not specified (seems one-to-one from the layout)

## Extension (Prerequisite / Billing):
Not Prerequisite

## Design Choices:
The design captures the core hospital workflow using four main entities: Patient, Appointment, Doctor, and Treatment.
Relationships like Books, Conducted by, and Visit logically link these entities.
All attributes shown are atomic and suitable for normalization.

## RESULT
The ER model represents a hospital database with four main entities—Patient, Doctor, Appointment, and Treatment—connected through three relationships: Books, Conducted by, and Visit. Each entity contains relevant attributes, and the model clearly outlines the flow of a hospital visit: a patient books an appointment, a doctor conducts it, and treatment follows. No billing or prerequisites are included in the diagram. The design is simple, logical, and aligns with real-world hospital processes as visually depicted.
