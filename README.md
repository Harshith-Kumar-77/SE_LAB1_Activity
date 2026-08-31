# SE Lab 1 – Problem Statement #62
## Food Bank Surplus Redistribution Platform

**Course:** Software Engineering Lab – Lab 1: Requirements Engineering & UML Use-Case Modelling  
**Problem:** Problem Statement #62 – Sustainability & Green Tech

### Scenario
A food rescue platform where restaurants and grocery stores post surplus edible food batches, and verified local shelters reserve pickup windows before food expiry.

### Actors
1. Donor Partner
2. Shelter Coordinator
3. Notification Service (external system actor used to model push notifications)

### Repository contents
- `docs/Requirements_Table.docx` – submission-ready requirements table.
- `docs/Requirements_Table.xlsx` – editable spreadsheet version.
- `docs/Requirements_Specification.md` – requirements in Markdown.
- `docs/Use_Case_Flow.docx` – one-page use-case flow.
- `docs/Use_Case_Flow.pdf` – PDF version for submission.
- `diagrams/UML_Use_Case_Diagram.pdf` – UML use-case diagram.
- `diagrams/UML_Use_Case_Diagram.png` – diagram image.
- `diagrams/use_case_diagram.puml` – PlantUML source.
- `diagrams/use_case_diagram.drawio` – editable draw.io source.
- `docs/Submission_Checklist.md` – final submission checklist.

### UML relationships used
- `<<include>>`: **Post Surplus Food Batch** includes **Validate Food Details** because validation is mandatory.
- `<<include>>`: **Reserve Pickup Window** includes **Verify Shelter Eligibility** because only verified shelters can reserve.
- `<<extend>>`: **Send Nearby Shelter Notification** extends **Post Surplus Food Batch** when the listed food is high-quantity and perishable.

### Core use case
**UC-04 – Reserve Pickup Window**

The flow document contains Preconditions, Postconditions, a Main Success Scenario, and an Alternate Flow for an expired/unavailable batch.

### Submission mapping
This project follows the Lab 1 handout requirement for exactly **5 Functional Requirements** and **2 Nonfunctional Requirements**, plus a UML use-case diagram and one use-case flow. The problem statement supplies FR-001 and NFR-001; the remaining requirements are drafted for this scenario.
