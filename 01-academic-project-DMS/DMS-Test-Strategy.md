# Test Strategy — FPT Dormitory Management System (DMS)

**Project:** Student Dormitory Management System, FPT University Da Nang
**Stack under test:** ReactJS (frontend) · Node.js (backend) · MongoDB (database)
**My role:** QC / Manual Tester in a 4-person testing team (alongside 3 teammates), responsible for a defined slice of the module set — see `Test-Cases/` for exactly which ones.

> This document summarizes the team's overall test approach. It is shared context for a
> group capstone project, not a claim of individual authorship over every section below —
> my personal, verifiable contributions are the files listed under `Test-Cases/`.

---

## 1. Scope

Testing covered both **system functionality** and **UI/UX quality**, with an additional
pass for **security** (role-based access control across Guest, Student, Manager,
Security, and Admin roles). The goal was to catch functional defects and access-control
gaps before release, across four sequential rounds of regression.

## 2. Test Strategy

The team prioritized **functional testing** — verifying the system behaves exactly as
specified in the requirements analysis — supported by three other test types:

| Test Type | Purpose |
|---|---|
| Functional Testing | Validate inputs/outputs and detect defects, independent of internal code structure |
| UI Testing | Confirm the interface is smooth and defect-free |
| Security Testing | Confirm role-based access control is correctly enforced |
| Usability Testing | Confirm each role (Guest, Student, Manager, Admin) can complete tasks efficiently |

## 3. Test Levels

| Test Type | Unit | Integration | System |
|---|:---:|:---:|:---:|
| Functional | X | X | X |
| UI | | | X |
| Security | X | X | |
| Usability | | | X |

## 4. Tools Used

| Purpose | Tool |
|---|---|
| API testing | Postman |
| Browser inspection | Chrome DevTools |
| Frontend hosting | Vercel |
| Backend hosting | Microsoft Azure |
| Database | MongoDB Atlas |
| Unit test execution | Jest |
| Test case documentation | Excel / Google Sheets |
| CI/CD | GitHub Actions |

## 5. My Personal Contribution

Out of the system's ~65 functions and 417 total test cases (across the 4-person team),
I personally:

- **Authored and executed Unit Test suites for 13 functions**, spanning authentication
  (Google Sign-in, Logout), student features (Booking, Utility Usage, Register Visitor
  Info, Chat with Manager, Chat with Student), and admin/manager operations (Login-as,
  Import/Export data, Import User Account). See `Test-Cases/DMS-UnitTest-13Functions.xlsx`.
- **Executed 6 functional/system test cases** for the Security module's
  **View Visitor Information** feature — including a negative test confirming
  non-security roles are correctly denied access (403). See
  `Test-Cases/DMS-SystemTest-VisitorInfo.xlsx`.

Full test case detail, results across 3 regression rounds, and pass/fail status are in
the linked spreadsheets.
