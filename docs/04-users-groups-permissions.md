# ArchMedica Users, Groups and Permissions

This document records the users, groups and permissions of the server.

## Groups:

This lab was designed with all of the following roles in mind:

    - it
    - patient
    - doctor
    - nurse
    - billing
    - wheel

### IT:
They have access to the whole server. They do not usually work with PII or PHI, however, since they are in charge of the server they should be able to access any directory

### Patient:
This is the patient role. They can see the medical records but they can't change them. They are also able to check their bills and upload payment information and other documents like insurance cards, SSN and other documentation.

### Doctor:
The doctor role can write clinical records, prescriptions, and procedures into the patient directory. PII is restricted for this role since a doctor should not be able to see credit card information or SSN

### Nurse:
The role of the nurse is to analyze docotor's notes, however, they can't change any details of the notes. PII is also restricted for this role

### Billing:
Billing is in charge of billing the patient. They can write medical bills and can see credit card information to proceed with the payment, but all of the PHI is restricted.

### Wheel:
The default sudo group of Arch Linux, this group only has one user, the admin user and the purpose of this role is to break the server and recover it as a practice. 

## Users

    it01 - it
    it02 - it

    doc01 - doctor
    doc02 - doctor

    pac01 - nurse
    pac02 - nurse

    pat01 - patient
    pat02 - patient

    bill01 - billing
    bill02 - billing

    admin - wheel

Nurse useres are called "pac" instead of "nur" or something similar because the name is a reference to their title: "Physician Assistan Certified"

## Disclaimer

A real hospital is more complex than this lab, doctors can access insurance cards of their patients, billing has access to procedures to start the billing proccess, and there is a lot of administrative roles.
This lab was intentionally simplified only for educational purpose and do not reflect the reality of an actual hospital. 




