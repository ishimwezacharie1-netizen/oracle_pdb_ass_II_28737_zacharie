# oracle_pdb_ass_II_28737_zacharie

This repository contains the Oracle PDB assignment materials, including the assignment PDF and a complete screenshot sequence showing the database workflow.

## Project overview

The assignment focuses on creating, verifying, and deleting a pluggable database (PDB) in an Oracle environment. The workflow includes:

- connecting to a local Oracle database
- switching to the container database
- creating a pluggable database named `ZA_PDB_28737`
- checking the list of available PDBs with `SHOW PDBS;`
- dropping the PDB and its data files
- confirming the final database state after deletion

## Folder contents

- [Assignment_II_Oracle_PDB_Organized 17-09-2026.pdf](Assignment_II_Oracle_PDB_Organized%2017-09-2026.pdf)
- [screen shot](screen%20shot)

## Assignment summary

The main SQL flow used in this assignment is:

```sql
ALTER SESSION SET CONTAINER = CDB$ROOT;
SELECT SYS_CONTEXT('USERENV', 'CON_NAME') AS CONTAINER_NAME FROM DUAL;

CREATE PLUGGABLE DATABASE za_pdb_28737
ADMIN USER zacharie_plsqlauca_28737 IDENTIFIED BY 200315
FILE_NAME_CONVERT = (
  'C:\app\oradata\ORCL\pdbseed',
  'C:\app\oradata\ORCL\za_pdb_28737'
);

SHOW PDBS;
DROP PLUGGABLE DATABASE za_to_delete_pdb_28737 INCLUDING DATAFILES;
SHOW PDBS;
```

## Visual workflow

### 1. Oracle database connection setup

![Oracle connection setup](screen%20shot/1.png)

This screenshot shows the Oracle connection form used to connect to the local database instance.

### 2. New database connection and login

![Database connection form](screen%20shot/2.png)

The database connection was configured and tested successfully before running the assignment commands.

### 3. Creating the pluggable database

![PDB creation script](screen%20shot/3.png)

This step shows the creation of the new pluggable database and the configuration of the file conversion path.

### 4. Verifying the PDB list

![PDB validation](screen%20shot/4.png)

The result confirms that the new PDB is visible in the container database after creation.

### 5. Dropping the PDB

![PDB removal process](screen%20shot/5.png)

The assignment demonstrates removing the pluggable database together with its data files.

### 6. Final confirmation after deletion

![Final confirmation](screen%20shot/6.png)

This final screenshot confirms the database state after the PDB has been removed.

## Final notes

This work demonstrates the essential Oracle PDB lifecycle:

1. create the pluggable database
2. confirm it appears in the list
3. remove it cleanly with data files
4. verify the final state

The included screenshots provide a clear visual record of each step in the assignment.
