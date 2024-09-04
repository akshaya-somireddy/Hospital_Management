**Hospital Management Project**

**Project Overview**
This project implements a hospital management system using PostgreSQL. It covers various aspects of hospital operations, including patient management, doctor scheduling, 
appointments, medical history, and diagnoses.

**Schema and Tables**
1. Schema
hospital_management: Contains all tables related to the hospital management system.
2. Tables
patient: Stores patient details such as email, password, name, address, and gender.

Primary Key: email
medical_history: Contains records of medical history, including conditions, surgeries, and medications.

Primary Key: medical_history_id
doctor: Stores doctor details including email, gender, password, and name.

Primary Key: email
appointment: Manages appointment details such as date, start time, end time, and status.

Primary Key: appointment_id
patient_visits: Records patient visits, including concerns, symptoms, and linked appointment details.

Primary Key: patient, appt
Foreign Keys: patient references patient(email), appt references appointment(appointment_id)
schedule: Manages doctor schedules, including start time, end time, break time, and day.

Primary Key: schedule_id, start_time, end_time, break_time, day
patients_history: Links patients with their medical history.

Primary Key: history
Foreign Keys: patient references patient(email), history references medical_history(medical_history_id)
diagnose: Stores diagnosis information, including appointment ID, doctor, diagnosis, and prescription.

Primary Key: appt, doctor
Foreign Keys: appt references appointment(appointment_id), doctor references doctor(email)
doctor_schedules: Associates doctors with their schedules.

Primary Key: sched, doctor
Foreign Keys: sched references schedule(schedule_id), doctor references doctor(email)
doctor_view_history: Records instances of doctors viewing a patient's medical history.

Primary Key: history, doctor
Foreign Keys: doctor references doctor(email), history references medical_history(medical_history_id)

**Installation and Setup**
Clone the repository:
git clone https://github.com/akshaya-somireddy/hospital-management.git

**Navigate to the project directory:**
cd hospital-management

**Database Setup:**

Ensure you have PostgreSQL installed.

Run the SQL script to create the schema and tables:

psql -U akshaya-somireddy -f hospital_management.sql

Usage
The database is ready to use for hospital management operations. You can insert data, query records, and manage hospital operations as needed.
