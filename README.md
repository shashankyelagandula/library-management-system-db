# 📚 Library Management System

This repository contains the **database design, implementation, and sample data** for a Library Management System, developed as the final project for **CS504: Principles of Data Management and Mining** at George Mason University.

---

## 📌 Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Database Design](#database-design)
  - [Entities and Attributes](#entities-and-attributes)
  - [Relationships](#relationships)
  - [Schema](#schema)
- [Data](#data)
- [Future Enhancements](#future-enhancements)
- [Team](#team)
- [License](#license)
- [Sources](#sources)

---

## 🧠 Project Overview

The objective of this project is to design and implement a functional **database management system** for a public library. This system helps library staff manage their resources, including books, magazines, digital media, and other materials. It also provides efficient access to library member information and facilitates the borrowing and tracking of library materials, ensuring **data integrity** and minimizing redundancy.

The scope includes the administration of:
- Library resources
- Catalogs
- Genres
- Writers and authorship connections
- Patrons
- Personnel

---

## ✨ Features

The Library Management System includes the following key features:

- **Materials Management**: Stores and maintains information about all library materials (books, magazines, e-books, audiobooks), including titles, authors, publication dates, and genres.
- **Membership Management**: Stores and manages information about library members, including names, contact information, membership numbers, and borrowing history.
- **Borrowing System**: Facilitates the borrowing process, allowing members to check out items and enabling tracking of overdue items.
- **Reservation System**: Allows members to reserve materials that are currently unavailable.
- **Staff Management**: Manages information about library staff, including their roles and responsibilities.
- **Reporting and Analytics**: Generates reports on borrowing trends, popular materials, and overdue items to assist in library management.
- **Overdue Alerts**: Alerts staff about overdue materials on a daily basis.
- **Automatic Membership Deactivation/Reactivation**: Automatically deactivates membership if a member has three or more overdue occurrences and reactivates it once the overdue fee is paid.

---

## 🗃️ Database Design

### Entities and Attributes

The core entities and their attributes are:

- **Material**: `Material_ID` (PK), `Title`, `Publication_Date`, `Catalog_ID` (FK), `Genre_ID` (FK)
- **Catalog**: `Catalog_ID` (PK), `Name`, `Location`
- **Genre**: `Genre_ID` (PK), `Name`, `Description`
- **Borrow**: `Borrow_ID` (PK), `Material_ID` (FK), `Member_ID` (FK), `Staff_ID` (FK), `Borrow_Date`, `Due_Date`, `Return_Date`
- **Author**: `Author_ID` (PK), `Name`, `Birth_Date`, `Nationality`
- **Authorship**: `Authorship_ID` (PK), `Author_ID` (FK), `Material_ID` (FK)
- **Member**: `Member_ID` (PK), `Name`, `Contact_Info`, `Join_Date`
- **Staff**: `Staff_ID` (PK), `Name`, `Contact_Info`, `Job_Title`, `Hire_Date`
- **Alerts**: `Alert_ID` (PK), `Material_ID`, `Member_ID`, `Alert_Date`, `Message`, `Is_Notified`

### Relationships

- **Material and Catalog**: A Material belongs to a Catalog (N:1)
- **Material and Genre**: A Material belongs to a Genre (N:1)
- **Material and Borrow**: Borrow references Material (N:1)
- **Borrow and Member**: Borrow references Member (N:1)
- **Borrow and Staff**: Borrow references Staff (N:1)
- **Author and Authorship**: Authorship references Author (N:1)
- **Material and Authorship**: Authorship references Material (N:1)

### Schema

- **ER Diagram**: _See `ER Diagram.png`_  
- **Relational Schema**: _See `Relational Schema.png`_

---

## 📁 Data

Sample data for the following tables is provided in `.csv` format:

- `Material.csv`
- `Member.csv`
- `Genre.csv`
- `Staff.csv`

---

## 🚀 Future Enhancements

- **User Interface**: Develop a graphical UI for easier staff/member interaction.
- **Advanced Reporting**: Add dashboards and custom reporting tools.
- **Search Functionality**: Implement fuzzy/full-text search across materials and members.
- **Notifications**: Integrate email or in-app notifications for alerts and reservations.

---

## 👥 Team

- **Shashank Yelagandula** (G01395790)

---

## 📄 License

This project is licensed under the terms provided by the instructor for **CS504: Principles of Data Management and Mining**.

---

## 📚 Sources

- Course material and database design principles from **CS504**
- Public documentation and database best practices
