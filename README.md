# Oracle_pdb_ass_II_29844_cyusa
## Student Details
CYUSA Bruno
29844
PL/SQL / Oracle Database Management

## Oracle Environment Used
* **Database Version:** Oracle Database 21c Enterprise Edition Release 21.3.0.0.0[cite: 2]
* **Management Tool:** Oracle Enterprise Manager (OEM)
  
# Assignment II: Oracle Pluggable Databases (PDB) Management

## Overview
This repository contains the required screenshots and documentation for Individual Assignment II, focusing on the creation of Oracle Pluggable Database (PDB) management, administrative tasks, and Enterprise Manager monitoring within an Oracle Database environment.  

* We will create a pluggable database, create a user inside the pdb and grant it privileges
* We will create a temporary pluggable database, and then delete it
* Lastly access Oracle Enterprise Manager/oem dashboard through port 5500


## Breakdown
### Task 1: Create a Pluggable Database (PDB) and Student User
* **PDB Name:** `cy_pdb_29844`
* **User Account Created:** `cyusa_plsqlauca_29844`
* **Actions Performed:** 
  1. Created the PDB using the administrative seed configuration.
  2. Opened the PDB and executed `SAVE STATE` to ensure it opens automatically on instance restart.
  3. Created a dedicated student user inside the PDB and granted appropriate privileges (`CREATE SESSION`, `CREATE TABLE`, `UNLIMITED TABLESPACE`).
# Evidence: this screenshot contains the creation of the pdb

  <img width="13900" height="4789" alt="pdb_creation (2)" src="https://github.com/user-attachments/assets/ad4053f9-c790-472d-870d-55ae70db458d" />  

  In the screenshot you will see the first command showing the identified path and the second command will show the pdb creation.  

Below you will see a command to put pdb in open state and saving the status so that it can be active always, since we are going to be using it a lot of times.  
<img width="682" height="230" alt="altering " src="https://github.com/user-attachments/assets/e9485d90-fa61-4092-8d94-53cae05677b2" />

And lastly the command to create a user inside the pdb named cyusa_plsql_29844 and granting it unlimited tablespace.  
<img width="935" height="311" alt="pdb_user_creation" src="https://github.com/user-attachments/assets/7f0ee8a6-b4ec-4bed-88fa-6c836092dcc1" />



# Task 2: Create and Delete a Temporary PDB
* **Temporary PDB Name:** `cy_to_delete_pdb_29844`[cite: 1]
* **Actions Performed:**
  1. Created a temporary PDB following the mandatory naming convention.
  2. Verified its existence and open status via data dictionary views (`V$PDBS`).
  3. Cleanly closed and dropped the PDB using the `INCLUDING DATAFILES` clause to completely wipe its resources.
# Evidence: this screenshot contains the creation of the temporary pdb  
<img width="1911" height="330" alt="deletepdb created-errortoo" src="https://github.com/user-attachments/assets/20688f66-efc6-46fa-a40e-cc1dbc49bacb" />
You will see that the first command will trigger an error because i have not added file name convert path but in the second command you will see that i added it and the command worked.

## below you will see command to close and delete the temporary pdb  
  <img width="936" height="792" alt="pdb_deletion" src="https://github.com/user-attachments/assets/b7823a29-cd0f-4d96-a1b1-a6cb1d2033df" />
First command will be to remove it from open state and close it, then second command was to drop it (delete it) and last command was to check if the temporary pdb was successfully deleted.  


# Task 3: Oracle Enterprise Manager (OEM) Dashboard
* **Actions Performed:**
  1. Authenticated into Oracle Enterprise Manager Database Express via port `5500`.
  2. Verified overall database performance metrics, resource utilization, and container status (`CY_PDB_29844` and `ORCLPDB`).
# Evidence: this screenshot contains the OEM dashboard
  <img width="1917" height="1036" alt="oem_dashboard" src="https://github.com/user-attachments/assets/bb499ac3-4faa-461a-8db4-79843a19211d" />


## Challenges Faced & Solutions
1. **Password Special Characters & Syntax (`ORA-00922`):** When creating the PDB with administrative credentials containing special characters or punctuation, trailing commas caused syntax issues. This was resolved by properly structuring the SQL clause and quoting password strings where necessary.  
2. **Missing File Mapping (`ORA-65016`):** Handled directory mapping requirements during container creation to ensure the physical data files mapped correctly.
3. **Container Authentication:** Ensured authentication defaulted properly to the root container (`CDB$ROOT`) during OEM login to access global performance tracking metrics.

# Integrity statement  
I confirm that this work is my own, completed independently in accordance with course guidelines and academic integrity standards. All tasks, scripts, and screenshots were generated and captured by me.

# Submission details block  
Repository Link:   https://github.com/BLACK-ICEMAN/oracle_pdb_ass_II_29844_cyusa  

PDB Name Created:  cy_pdb_29844  

Issues Encountered: Yes (Addressed syntax error and container path configuration [file_name_convert])

