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


## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

## Scenario Chosen:
Hospital

## ER Diagram:
![Screenshot 2025-04-28 135107](https://github.com/user-attachments/assets/dc660600-e508-424a-95ed-d6d8b63d022e)



## Entities and Attributes:

- **Doctor**:  
  - Doctor ID (Primary Key)  
  - Name  
  - Phone  
  - Specialization

- **Patient**:  
  - Patient ID (Primary Key)  
  - Name  
  - Phone  
  - Address
  - Insurance details

- **Department**:  
  - Dept ID (Primary Key)  
  - Dept Name  
  - Dept Head

- **Appointment**:  
  - Appointment ID (Primary Key)  
  - Patient ID (Foreign Key)  
  - Doctor ID (Foreign Key)  
  - Appointment Date and Time  
  - Reason for Visit

- **Medical Record**:  
  - Medical record
  - Patient ID (Foreign Key)  
  - Treatment
  - Diagnosis
  - Result
---

## Relationships and Constraints:

- **Assigned to** (Doctor - Department):  
  - 1 Department → M Doctors  
  - (1:M cardinality)

- **Conducts** (Doctor - Appointment):  
  - 1 Doctor → M Appointments  
  - (1:M cardinality)

- **Schedule** (Patient - Appointment):  
  - 1 Patient → M Appointments  
  - (1:M cardinality)

- **Has Records** (Patient - Medical Record):  
  - 1 Patient → M Medical Records  
  - (1:M cardinality)

- **Creates Record** (Doctor - Medical Record):  
  - 1 Doctor → M Medical Records  
  - (1:M cardinality)

---

## Extension (Prerequisite / Billing):

- **Billing**:  
  **(Note: Billing is not shown in the current diagram.)**  
  To incorporate billing, a **Billing** entity could be created with attributes such as Billing ID, Appointment ID, Amount Charged, Payment Status, and Payment Date.  
  This would connect directly to the **Appointment** entity because billing usually follows an appointment.


## Design Choices:

- **Separate Department Entity**:  
  Departments are distinct from Doctors to normalize and manage department-specific information efficiently.

- **Appointment Entity**:  
  The Appointment entity connects Doctors and Patients and captures critical transactional data like the date, time, and reason for the appointment.

- **Medical Record as Separate Entity**:  
  Medical Records are separated from appointments because a patient might have multiple medical records (for multiple visits or conditions), and they must be accessed independently.

- **Clear Specialization Handling**:  
  The Doctor entity includes Specialization directly as an attribute to simplify queries related to doctor expertise without a separate Specialization table.

- **M:1 and 1:M Relationships**:  
  Relationships reflect the real-world situation where one patient can have multiple appointments and records, and one doctor can handle multiple appointments and medical records.


## RESULT:

The ERD effectively models the hospital appointment system, clearly separating key aspects like scheduling, department assignment, and medical history tracking, ensuring scalability and ease of future extensions like billing and lab test integration.
