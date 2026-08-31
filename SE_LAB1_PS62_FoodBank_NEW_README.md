# Software Engineering Lab 1
## Food Bank Surplus Redistribution Platform

**Problem Statement #62 – Sustainability & Green Tech**

---

## 1. Project Overview

The Food Bank Surplus Redistribution Platform is a food rescue platform where restaurants and grocery stores can post surplus edible food batches, while verified local shelters can reserve pickup windows before the food expires.

The main objective of the platform is to support efficient redistribution of surplus food and reduce food wastage by connecting donors with verified shelters.

---

## 2. Problem Statement

A food rescue platform where restaurants and grocery stores post surplus edible food batches, and verified local shelters reserve pickup windows before food expiry.

### Target Stakeholders / Actors

- **Donor Partner**
- **Shelter Coordinator**

An external **Notification Service** is also modeled to represent push notifications to nearby shelters.

---

## 3. Functional Requirements

The project contains exactly five Functional Requirements as required for Lab 1.

| ID | Requirement |
|---|---|
| FR-001 | The system shall allow donors to post surplus food packages with perishable expiry countdown timers and dietary tags. |
| FR-002 | The system shall allow verified shelters to browse and filter active surplus food batches. |
| FR-003 | The system shall allow a verified shelter to reserve an available food batch and select a pickup window before expiry. |
| FR-004 | The system shall allow authorized donors and shelter coordinators to view reservation status and the pickup verification code. |
| FR-005 | The system shall automatically mark a food batch as expired and prevent further reservation when its expiry time is reached. |

---

## 4. Non-Functional Requirements

The project contains exactly two Non-Functional Requirements.

| ID | Requirement |
|---|---|
| NFR-001 | The platform shall dispatch instant push notifications to shelters within a 5 km radius when high-quantity perishable food is listed. |
| NFR-002 | The platform shall protect donor and shelter account data using authenticated role-based access control, with reservation actions recorded with timestamps. |

---

## 5. Actors

### Donor Partner
- Registers/verifies the donor account.
- Posts surplus food batches.
- Views reservation and verification information.

### Shelter Coordinator
- Registers/verifies the shelter.
- Browses available food batches.
- Reserves pickup windows.
- Views reservation and verification information.

### Notification Service
- Sends notifications to eligible nearby shelters when high-quantity perishable food is posted.

---

## 6. Use Cases

The UML model contains the following use cases:

- **UC-01 – Register / Verify Partner**
- **UC-02 – Post Surplus Food Batch**
- **UC-03 – Browse Available Batches**
- **UC-04 – Reserve Pickup Window**
- **UC-05 – View Reservation & Verification Code**
- **UC-06 – Mark Batch Expired**
- **UC-07 – Send Nearby Shelter Notification**
- **UC-08 – Validate Food Details**
- **UC-09 – Verify Shelter Eligibility**

---

## 7. UML Relationships

### `<<include>>` Relationship

**UC-02 – Post Surplus Food Batch**  
`<<include>>`  
**UC-08 – Validate Food Details**

Food details must be validated before a surplus batch can be posted.

### `<<include>>` Relationship

**UC-04 – Reserve Pickup Window**  
`<<include>>`  
**UC-09 – Verify Shelter Eligibility**

Shelter eligibility must be verified before a reservation can be completed.

### `<<extend>>` Relationship

**UC-07 – Send Nearby Shelter Notification**  
`<<extend>>`  
**UC-02 – Post Surplus Food Batch**

The notification behavior is triggered when the posted food is high-quantity and perishable.

---

## 8. Core Use Case

### UC-04 – Reserve Pickup Window

The Shelter Coordinator selects an available surplus food batch and reserves a suitable pickup window before the food expires.

### Preconditions

- The Shelter Coordinator is authenticated.
- The shelter is verified.
- The selected food batch is active and available.
- The food batch has not expired.

### Postconditions

- The food batch is reserved.
- The selected pickup window is recorded.
- A unique pickup verification code is generated.
- Authorized users can view the reservation information.

### Main Success Scenario

1. The Shelter Coordinator opens the list of active surplus food batches.
2. The system displays available batches with quantity, dietary tags, location, and expiry countdown.
3. The Shelter Coordinator selects a suitable food batch.
4. The system verifies the shelter and checks that the batch is still available.
5. The Shelter Coordinator selects an available pickup window before expiry.
6. The system creates the reservation.
7. The system marks the batch as reserved.
8. The system generates a unique pickup verification code.
9. The system displays the reservation confirmation and verification code.
10. The use case ends successfully.

### Alternate Flow – Expired or Already Reserved Batch

1. The system detects that the selected batch has expired or has already been reserved.
2. The reservation request is rejected.
3. The system displays the reason to the Shelter Coordinator.
4. The batch is removed from the reservable list.
5. The Shelter Coordinator can select another available batch.

---

## 9. Repository Structure

```text
SE-LAB-1/
│
├── diagrams/
│   ├── UML_Use_Case_Diagram.pdf
│   ├── UML_Use_Case_Diagram.png
│   └── use_case_diagram.puml
│
├── docs/
│   ├── Problem_Statement.pdf
│   ├── Requirements_Specification.md
│   ├── Requirements_Table.docx
│   ├── Requirements_Table.xlsx
│   ├── Use_Case_Flow.docx
│   └── Use_Case_Flow.pdf
│
└── README.md
```

---

## 10. Project Files

### `docs/Problem_Statement.pdf`
Contains the provided Problem Statement #62.

### `docs/Requirements_Specification.md`
Contains the complete functional and non-functional requirements specification.

### `docs/Requirements_Table.docx`
Editable Word version of the requirements table.

### `docs/Requirements_Table.xlsx`
Editable Excel version of the requirements table.

### `docs/Use_Case_Flow.docx`
Editable Word document containing the core use-case flow.

### `docs/Use_Case_Flow.pdf`
PDF version of the use-case flow for submission.

### `diagrams/UML_Use_Case_Diagram.pdf`
Final UML use-case diagram in PDF format.

### `diagrams/UML_Use_Case_Diagram.png`
Image version of the UML use-case diagram.

### `diagrams/use_case_diagram.puml`
PlantUML source file for the UML diagram.

---

## 11. Lab 1 Deliverables

- [x] Exactly 5 Functional Requirements
- [x] Exactly 2 Non-Functional Requirements
- [x] Requirement IDs FR-001 to FR-005
- [x] Requirement IDs NFR-001 to NFR-002
- [x] Requirement descriptions
- [x] Priorities
- [x] Acceptance criteria
- [x] Rationales
- [x] At least 3 actors
- [x] At least 5 use cases
- [x] `<<include>>` relationship
- [x] `<<extend>>` relationship
- [x] UML Use-Case Diagram
- [x] Use-Case Flow
- [x] Preconditions
- [x] Postconditions
- [x] Main Success Scenario
- [x] Alternate Flow

---

## 12. Submission

The complete Lab 1 project is organized into `docs`, `diagrams`, and `README.md`.

Before final submission:

1. Add your **Name, SRN, Section and Date** wherever required.
2. Check all documents for formatting.
3. Verify the UML diagram.
4. Verify the requirements table.
5. Verify the one-page use-case flow.
6. Push all files to the Lab 1 GitHub repository.

---

**Software Engineering Lab 1**  
**Problem Statement #62 – Food Bank Surplus Redistribution Platform**
