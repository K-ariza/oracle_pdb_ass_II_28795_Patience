<span style="color:#1F77B4">Oracle Pluggable Database Assignment II</span>
<span style="color:#1F77B4">Student Information</span>

Name: KARIZA PARIENCE

Student ID:28795

Course: Database Development with PL/SQL (INSY 8311)

### <span style="color:#2CA02C">Tasks Completed:</span>
1. Create a new Pluggable Database (PDB)
2. Switch to and verify the created PDB
3. Verify user existence within the PDB
4. Create a temporary PDB for testing purposes
5. Verify the temporary PDB was created successfully
6. Drop the temporary PDB and verify removal
7. Access Oracle Enterprise Manager (OEM) for database monitoring

---


## <span style="color:#1F77B4">Oracle Environment</span>

| Property | Details |
|----------|---------|
| **Oracle Version** | Oracle 21c |
| **Operating System** | Windows 10 |
| **Container Database** | ORCL21 |
| **Storage Location** | C:\oracle21c\oradata\ORCL21 |



## <span style="color:#9467BD">Task Explanations</span>

### <span style="color:#1F77B4">Task 1: PDB Creation</span>

Creates a new pluggable database named `pa_pdb_28795` within the container database. 
A new pluggable database named was created within the container database following the required naming format. The PDB was successfully opened, and the administrative user `patience_plsqlauca_28795` was created for future class activities.



PDB creation command

```sql
CREATE PLUGGABLE DATABASE pa_pdb_28795
ADMIN USER patience_plsqlauca_28795 IDENTIFIED BY "Karo@987#564451" 
FILE_NAME_CONVERT = ('C:\oracle21c\oradata\ORCL21\pdbseed','C:\oracle21c\oradata\ORCL21\pa_pdb_28795'); 

ALTER SESSION SET CONTAINER = pa_pdb_28795;
SHOW CON_NAME;


SELECT username FROM dba_users
WHERE username = 'patience_plsqlauca_28795';


```
Screenshot evidence shows:

![Task 1](<https://github.com/K-ariza/oracle_pdb_ass_II_28795_Patience/blob/main/Screenshot/Create%20PDB.png>)

### <span style="color:#1F77B4">Task 2: Temporary PDB Creation and Deletion</span>


A temporary pluggable database named `pa_to_delete_pdb_28795` was created to demonstrate PDB lifecycle management. After verifying its existenced and dropped completely, including its data files.


Temporary PDB creation

```sql
CREATE PLUGGABLE DATABASE pa_to_delete_pdb_28795
ADMIN USER karo IDENTIFIED BY Karo1234 
FILE_NAME_CONVERT = ('C:\oracle21c\oradata\ORCL21\pdbseed','C:\oracle21c\oradata\ORCL21\pa_to_delete_pdb_28795'); 

SHOW PDBS;


DROP PLUGGABLE DATABASE ka_to_delete_pdb_2024101 INCLUDING DATAFILES;
SHOW PDBS;



```


Verification using SHOW PDBS


 ![Task 2](<https://github.com/K-ariza/oracle_pdb_ass_II_28795_Patience/blob/main/Screenshot/Create%20T%20PDB.png>)


Successful deletion and confirmation


 ![Task 3 ](<https://github.com/K-ariza/oracle_pdb_ass_II_28795_Patience/blob/main/Screenshot/Drop%20T%20PDB.png>)


### <span style="color:#1F77B4">Task 7: Oracle Enterprise Manager (OEM)</span>

Oracle Enterprise Manager was accessed successfully to monitor and manage the Oracle database environment. The dashboard displayed the created PDB and confirmed the active database configuration.

A screenshot of the OEM dashboard is included as proof.

![Task 4](<https://github.com/K-ariza/oracle_pdb_ass_II_28795_Patience/blob/main/Screenshot/OEM.jpeg>)

## <span style="color:#1F77B4">Challenges Faced and Solutions</span>

### <span style="color:#1F77B4">Challenge: Oracle Installation Issues</span>

Problem: Initially encountered errors while opening the PDB after creation.

Solution:

Verified container context using SHOW CON_NAME

Ensured correct session switching to CDB$ROOT before PDB operations

Re-executed commands carefully following naming conventions

Outcome: Successfully created, opened, and managed all required PDBs.

## <span style="color:#1F77B4">Integrity Statement</span>

I certify that this assignment is my own original work. All SQL commands were executed directly in my Oracle database environment, and all screenshots included in this repository are authentic evidence of my practical work. I followed all instructions and naming conventions as required.


## <span style="color:#1F77B4">Final Checklist (Apply Before Submission)</span>

- [x] Correct PDB names used
- [x] User created inside the PDB
- [x] Temporary PDB created and deleted
- [x] OEM dashboard screenshot included
- [x] GitHub repository is PUBLIC
- [x] README is clear and professional
- [x] Deadline respected

---

*End of Report*






