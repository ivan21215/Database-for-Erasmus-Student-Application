# Database: Erasmus Student Application

This Microsoft Access database (`baze_podataka_seminarski_rad.accdb`) is designed to manage data related to Erasmus student exchange, including information about universities, students, cities, internships, enrollment forms, activities, and institutions.

## 📚 Database Overview

The database contains multiple related tables with one-to-one and one-to-many relationships. Key tables include:

### 🔹 Activity (`Aktivnost`)
- `ID_Aktivnost` (primary key)
- `Datum_početka`, `Datum_završetka` (start/end dates)
- `Iznos_subvencije` (subsidy amount)
- `ime_aktivnost` (activity name)
- Linked to internships, classes, and final thesis

### 🔹 Country (`Država`)
- `ID_Država` (primary key)
- `Ime_Država` (country name)
- Linked to the `City` table

### 🔹 City (`Grad`)
- `ID_Grad`, `Ime_Grad`, `ID_Država`
- Related to: universities, internships, student data

### 🔹 University (`Faks`)
- `ID_faks`, `Faks_ime` (name), `Faks_adresa` (address), `ID_Grad`
- Connected with `Student`, `Smijer` (study major), and enrollment list

### 🔹 Erasmus University (`Erasmus_Faks`)
- `ID_erasmus_faks`, `Ime_faks`, `Adresa_faks`, `ID_Grad`
- Linked to `Erasmus_upisni_list`

### 🔹 Erasmus Enrollment Form (`Erasmus_upisni_list`)
- `ID_upisnog_lista`, `ID_student`, `ID_smijer`, `ID_aktivnost`
- Connected to nearly all other key entities

### 🔹 Internship (`Praksa`)
- `ID_praksa`, `Opis-rada` (work description), `početni_datum`, `završni_datum`, `ETCS_bodovi`
- Linked to `Firma` (company), `Grad`, and `Aktivnost`

### 🔹 Class Attendance (`Pohađanje nastave`)
- `ID_pohađanje_nastave`, `Ime_pohađanja`, `ID_smijer`
- Linked to `Activity`

### 🔹 Company (`Firma`)
- `ID_firma`, `ime_firma`, `adresa_firma`
- Related to internships

### 🔹 Study Major and Student (`Smijer`, `Student`)
- Tables tracking academic majors and student records

## 🔗 Relationships

The database uses a **relational model** with:
- One-to-one (1:1)
- One-to-many (1:N)
- Cascading updates and deletes for data integrity

## 🧩 Technologies

- Microsoft Access (`.accdb`)
- Uses primary keys, foreign keys, and indexing
- Can be extended to other platforms (e.g. Excel export or web apps)

## 📌 Note

This database was created as a **seminar project**, intended to demonstrate Erasmus program data management in an academic environment. It can be extended into a user interface or connected to a larger software system.

---

© 2025 – Author: [Ivan Ivković]
