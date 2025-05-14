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
NAME : PORKODI P
REGISTER NUMBER : 212223060199
## Scenario Chosen:
Hospital 

## ER Diagram:
![Screenshot (95)](https://github.com/user-attachments/assets/f16854f9-9c4f-400d-af1d-e503527e738a)


Here’s a step-by-step procedure of how this system operates based on the ER diagram:

Step-by-Step Procedure
Patient Registration:

Patient provides basic details: PatientID, Name, Gender, DateOfBirth.

Contact details like Address and Phone Number are also recorded.

Doctor Details Entry:

Each doctor has: DoctorID, Name, Specialization, and Address.

Booking an Appointment:

A patient books an appointment with a doctor.

An Appointment record is created with:

AppointmentID, Date, Time, Status

Links to PatientID and DoctorID.

Billing Generation:

Once an appointment occurs, it generates a bill.

A Billing record is created:

BillID, BillDate, TotalAmount

Linked to the AppointmentID.

Payment Processing:

The bill is paid by the patient.

A Payment record is generated with:

PaymentDate, AmountPaid, Status

Links to the BillID.

Entities and Relationships Summary:
Entity	Attributes
Patient	PatientID, Name, Gender, DateOfBirth
Doctor	DoctorID, Name, Specialization, Address
Appointment	AppointmentID, Date, Time, Status, Phone, Address
Billing	BillID, BillDate, TotalAmount
Payment	PaymentDate, AmountPaid, Status

Relationships:

Patient books Appointment (with Doctor).

Appointment generates Billing.

Billing paid by Payment.
## RESULT
Thus, the Entity-Relationship (ER) Diagram have been created successfully.
