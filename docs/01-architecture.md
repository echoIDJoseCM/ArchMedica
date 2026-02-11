# ArchMedica Architecture

This readme explains the architecture of the entire lab and the reason why all of these choices were made

## Server

- OS: Arch Linux [To see more details about the installation, please refer to the installation log md]
- Platform: Virtual Machine

The server was created following the next directory architecture:

- /srv : The location of the entire server

- /srv/archmedica
- /srv/archmedica/PHI
    - /srv/archmedica/PHI/Encounters
        - /srv/archmedica/PHI/Encounters/pat01
        - /srv/archmedica/PHI/Encounters/pat02
    - /srv/archmedica/PHI/Procedures
        - /srv/archmedica/PHI/Procedures/pat01
        - /srv/archmedica/PHI/Procedures/pat02
    
- /srv/archmedica/PII
    - /srv/archmedica/PII/Billing
        -srv/archmedica/PII/Billing/pat01
        -srv/archmedica/PII/Billing/pat02
    - /srv/archmedica/PII/Patient_Uploads
        -srv/archmedica/PII/Patient_Uploads/pat01
        -srv/archmedica/PII/Patient_Uploads/pat02

Encounters: Office visit with the doctor
Procedures: Medical procedures performed [MRI, CT SCAN, XRAY, etc...]
Billing: Patient bills
Patient_Uploads: Information uploaded by the patient [Insurance card, payment methods, credit card information, etc ...]


The servers was designed with 5 main roles in mind: health employees )(Doctors and nurses), billing employees, patients, IT and main administrator:
 - Health employees cannot access to PII (Personal Indentifiable Information).
 - Billing epmlpyees cannot access to PHI (Personal Healht Information).
 - Patient can access both, but only write in /Patient Updates.
 - IT can accses all of the information, only for technical purposes.
 - Main Administrator have full control of the server, is the only role with full sudo permissions.

To see a more detailed list about permissions and users, please refer to the users and permissions md

A real healthcare environment works completly different, docotors and billing have to share PII and PHI, including RCM and medical coders, however, this server was designed to be simple and educational.

The main administrator role have full control of the server because I will be running different tests with educational purposes using this role, like deleting all the server and recover it.


## Client

- OS: Linux Mint [To see more details about the installation, please referr to the client md]
- Platform: Virtual Machine

The client will have a basic python program that will connect to the server, the purpose of the program is to simulate a client.
This program will be a dummy program full of bugs and made with AI because software development is out of the scope of this lab.




