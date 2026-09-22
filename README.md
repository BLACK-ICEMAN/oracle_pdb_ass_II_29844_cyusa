# oracle_pdb_ass_II_29844_cyusa
## Student Details
CYUSA Bruno
29844
PL/SQL / Oracle Database Management

## Oracle Environment Used
* **Database Version:** Oracle Database 21c Enterprise Edition Release 21.3.0.0.0[cite: 2]
* **Management Tool:** Oracle Enterprise Manager (OEM)
  
# Assignment II: Oracle Pluggable Databases (PDB) Management

## Overview
This repository contains the required screenshots and documentation for Individual Assignment II, focusing on Oracle Pluggable Database (PDB) management, administrative tasks, and Enterprise Manager monitoring within an Oracle Database environment.  

## Breakdown
### Task 1: Create a Pluggable Database (PDB) and Student User
* **PDB Name:** `cy_pdb_29844`[cite: 1]
* **User Account Created:** `cyusa_plsqlauca_29844`[cite: 1]
* **Actions Performed:** 
  1. Created the PDB using the administrative seed configuration.
  2. Opened the PDB and executed `SAVE STATE` to ensure it opens automatically on instance restart.
  3. Created a dedicated student user inside the PDB and granted appropriate privileges (`CREATE SESSION`, `CREATE TABLE`, `UNLIMITED TABLESPACE`).
* **Evidence:** Screenshots stored in `screenshots/pdb_creation/`

# Task 2: Create and Delete a Temporary PDB
* **Temporary PDB Name:** `cy_to_delete_pdb_29844`[cite: 1]
* **Actions Performed:**
  1. Created a temporary PDB following the mandatory naming convention.
  2. Verified its existence and open status via data dictionary views (`V$PDBS`).
  3. Cleanly closed and dropped the PDB using the `INCLUDING DATAFILES` clause to completely wipe its resources.
* **Evidence:** Screenshots stored in `screenshots/pdb_deletion/`

# Task 3: Oracle Enterprise Manager (OEM) Dashboard
* **Actions Performed:**
  1. Authenticated into Oracle Enterprise Manager Database Express via port `5500`.
  2. Verified overall database performance metrics, resource utilization, and container status (`CY_PDB_29844` and `ORCLPDB`).
* **Evidence:** Dashboard screenshot stored in `screenshots/oem_dashboard/`

## Challenges Faced & Solutions
1. **Password Special Characters & Syntax (`ORA-00922`):** When creating the PDB with administrative credentials containing special characters or punctuation, trailing commas caused syntax issues. This was resolved by properly structuring the SQL clause and quoting password strings where necessary.
2. **Missing File Mapping (`ORA-65016`):** Handled directory mapping requirements during container creation to ensure the physical data files mapped correctly.
3. **Container Authentication:** Ensured authentication defaulted properly to the root container (`CDB$ROOT`) during OEM login to access global performance tracking metrics.

## Integrity Statement
I confirm that this work is my own, completed independently in accordance with course guidelines and academic integrity standards. All tasks, scripts, and screenshots were generated and captured by me.

# Submission Details 

Repository Link: [https://github.com/](https://github.com/)[Your-BLACK-ICEMAN]/oracle_pdb_ass_II_29844_cyusa
PDB Name Created: cy_pdb_29844
Issues Encountered: Yes (Addressed syntax and container path configuration)
