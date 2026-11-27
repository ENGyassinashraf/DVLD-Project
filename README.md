# Driving & Vehicle License Department (DVLD) Management System

![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=csharp&logoColor=white)
![.NET](https://img.shields.io/badge/.NET-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![Windows Forms](https://img.shields.io/badge/Windows%20Forms-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)
![ADO.NET](https://img.shields.io/badge/ADO.NET-Data%20Access-5C2D91?style=for-the-badge)

A desktop application built with **C#**, **Windows Forms**, **ADO.NET**, and **Microsoft SQL Server** following a **3-Tier Architecture** to streamline operations at a Driving & Vehicle License Department (DVLD). The system manages people, users, application workflows, driver testing, local and international driving licenses, and license detentions/releases.

---

## Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [System Architecture](#system-architecture)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation & Setup](#installation--setup)
- [Screenshots](#screenshots)
- [Future Improvements](#future-improvements)
- [Author](#author)

---

## Overview

The **DVLD Management System** digitizes core administrative and operational workflows required to register citizens/applicants, process service applications, schedule and record driving tests, issue and renew licenses, and enforce license restrictions.

By separating user interface components, business rules, and data access logic into distinct layers, the application remains modular, maintainable, and easier to extend as requirements grow.

---

## Key Features

### 1. People & User Management
- **People Directory:** Add, update, view details, search, and manage person records (national number, contact info, address, country, gender, date of birth, and profile image).
- **User Accounts & Authentication:** Create and manage system user accounts linked to person records, handle login authentication, update passwords, and control account activation status.

### 2. Application Types & Service Requests
- **Application Types Management:** View and update service fees and titles for system application types.
- **Local Driving License Applications:** Submit new local driving license requests, track application status (New, Cancelled, Completed), and prevent duplicate active applications for the same license class.
- **Retake Test Applications:** Handle application workflows when an applicant retakes a test after a previous attempt.

### 3. Driving Tests & Appointments
- **Test Types Configuration:** Manage test definitions (such as Vision Test, Written/Theory Test, and Practical/Street Test) along with descriptions and fees.
- **Test Appointments & Scheduling:** Schedule appointments for applicants, lock/track appointment status, and record pass/fail test results.
- **Progression Rules:** Enforce sequential test progression and validate eligibility before issuing a license.

### 4. License Lifecycle Management
- **Issue First-Time Local License:** Issue a local driving license once required tests and application steps are completed.
- **License Renewal:** Renew expiring or expired local licenses with validation checks and fee calculation.
- **Replacement for Lost or Damaged Licenses:** Issue replacement licenses for lost or damaged cards while deactivating superseded licenses.
- **International Driving Licenses (IDP):** Issue international driving permits for eligible local license holders and view issued international licenses.

### 5. Detain & Release Licenses
- **Detain License:** Place a hold/detention on an active license with detention reason and fine details.
- **Release Detained License:** Process release applications, record payment/release metadata, and restore license usability.
- **Detained Licenses List:** Search, filter, and review detained licenses and their release status.

### 6. History & Records Lookup
- **License History:** View a person's local and international license history.
- **Application & Driver Records:** Inspect detailed driver information, license cards, and application records across the system.

---

## System Architecture

The project is structured around a **3-Tier Architecture** (with reusable UI controls in the presentation tier):

```text
+-------------------------------------------------------+
|              Presentation Layer (UI)                  |
|       Windows Forms, User Controls, Input Validation  |
+---------------------------+---------------------------+
                            |
                            v
+-------------------------------------------------------+
|              Business Logic Layer (BLL)               |
|     Domain Entities, Business Rules, Workflow Checks  |
+---------------------------+---------------------------+
                            |
                            v
+-------------------------------------------------------+
|              Data Access Layer (DAL)                  |
|       ADO.NET (SqlConnection, SqlCommand, DataTable)  |
+---------------------------+---------------------------+
                            |
                            v
+-------------------------------------------------------+
|            Database Layer (SQL Server)                |
|        Tables, Constraints, Views / Stored Procs      |
+-------------------------------------------------------+
