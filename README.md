# Medical Practice Database and Appointment Analytics

> **Data notice:** All records in this repository are synthetic and are used only for educational and portfolio demonstration purposes. No real patient or practitioner information is included.

## Project Overview

This project demonstrates the design and implementation of a relational medical practice database using Microsoft SQL Server.

The database supports:

- Patient record management
- Practitioner record management
- Practitioner availability
- Appointment scheduling
- Operational reporting
- Reusable views and stored procedures
- Automated patient contact-date updates
- Data-quality validation
- One-way hashing of a synthetic sensitive identifier

## Business Problem

A medical practice requires a structured database to replace disconnected CSV files and support reliable management of patients, practitioners, availability, and appointments.

The solution provides a relational data model, reusable database objects, validation queries, and basic operational reporting.

## Technologies

- Microsoft SQL Server
- SQL Server Management Studio
- T-SQL
- CSV
- GitHub
- Power BI planned as an analytical extension

## Skills Demonstrated

- Relational database design
- Primary and foreign keys
- Data loading and validation
- SQL joins and aggregations
- Window functions
- Views
- Stored procedures
- Triggers
- Error handling
- SHA-256 hashing
- Technical documentation

## Database Structure

The database contains the following core tables:

- `Patient`
- `Practitioner`
- `PractitionerType`
- `WeekDays`
- `Availability`
- `Appointment`

## Entity Relationship Diagram

diagrams/medical_practice_erd.png

## Example Business Questions

The project answers questions such as:

- Which practitioners are available on each weekday?
- Which patients have had at least three appointments?
- Which patients have never had an appointment?
- Which practitioner has the highest appointment workload?
- How many days have passed since each patient's last appointment?
- Which nurses are scheduled to work on Wednesday?

## Repository Structure

```text
data/       Synthetic sample data
sql/        SQL Server scripts
docs/       Data dictionary and technical documentation
diagrams/   Entity relationship diagram
images/     Query and database screenshots
powerbi/    Dashboard documentation and future analytical work
```

## How to Run the Project

1. Open SQL Server Management Studio.
2. Connect to a local SQL Server instance.
3. Run the files in the `sql` folder in numerical order.
4. Review the validation results from `05_data_validation.sql`.
5. Run the business queries and database object demonstrations.

## Key Database Features

### Views

- `vwNurseDays`
- `vwNSWPatients`

### Stored Procedures

- `spSelect_vwNSWPatients`
- `spInsert_vwNSWPatients`
- `spModify_PractitionerMobilePhone`

### Trigger

- `tr_Appointment_AfterInsert`

### Security Demonstration

A synthetic licence identifier is transformed using SQL Server's `SHA2_256` hashing algorithm. This is presented as a learning demonstration and not as a complete production security design.

## Limitations

- The dataset is intentionally small.
- All data is synthetic.
