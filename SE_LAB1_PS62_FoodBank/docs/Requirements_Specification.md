# Requirements Specification – Problem Statement #62

## Functional Requirements

| Req ID | Type | Description | Priority | Acceptance Criteria | Rationale |
|---|---|---|---|---|---|
| FR-001 | Functional | The system shall allow donors to post surplus food packages with perishable expiry countdown timers and dietary tags. | High | Pass: A donor creates a valid surplus batch with quantity, expiry time, and dietary tags, and the batch appears on the claim board with a countdown. Fail: Any required field is missing or an expired batch remains active. | Core function for making edible surplus visible to verified shelters. |
| FR-002 | Functional | The system shall allow verified shelters to browse active surplus food batches and filter them by location, expiry time, quantity, and dietary tags. | High | Pass: A verified shelter can view only active batches and each selected filter changes the displayed results correctly. Fail: Expired batches are shown as reservable or a filter returns incorrect batches. | Helps shelters quickly find suitable food before it expires. |
| FR-003 | Functional | The system shall allow a verified shelter to reserve an available food batch and select an available pickup window before the batch expires. | High | Pass: A shelter reserves an available batch and receives a unique reservation/pickup verification code with the selected window. Fail: The system confirms a reservation after expiry or for an already reserved batch. | Connects surplus food with a confirmed local pickup. |
| FR-004 | Functional | The system shall allow the donor partner and shelter coordinator to view the reservation status and pickup verification code for a confirmed batch. | Medium | Pass: Both authorized parties can view the same confirmed reservation status and code. Fail: An unauthorized user can access the code or the two parties see inconsistent status. | Supports reliable handover and reduces pickup confusion. |
| FR-005 | Functional | The system shall automatically mark a food batch as expired and remove it from active reservation when its expiry time is reached. | High | Pass: At the configured expiry time, the batch status changes to Expired and it can no longer be reserved. Fail: An expired batch remains reservable. | Prevents unsafe or invalid claims after the food expiry deadline. |
| NFR-001 | Nonfunctional | The platform shall dispatch instant push notifications to shelters within a 5 km radius when high-quantity perishable food is listed. | High | Pass: In a benchmark with a high-quantity perishable listing, eligible shelters within 5 km receive the notification within the platform's configured instant-notification target and unauthorized recipients do not receive it. Fail: An eligible shelter is missed or an out-of-radius shelter receives the alert. | The supplied problem statement explicitly prioritizes rapid local notification for highly perishable surplus. |
| NFR-002 | Nonfunctional | The platform shall protect donor and shelter account data using authenticated role-based access control, and reservation actions shall be recorded with a timestamp. | High | Pass: Unauthenticated users cannot create or reserve batches; role-restricted actions are denied to unauthorized roles; each successful reservation stores user and timestamp. Fail: Any restricted action succeeds without authorization or no audit timestamp is recorded. | Food donations and reservation details should be accessible only to authorized participants and remain traceable. |

## Actors
- Donor Partner
- Shelter Coordinator
- Notification Service

## Primary Use Cases
- UC-01 Register / Verify Partner
- UC-02 Post Surplus Food Batch
- UC-03 Browse Available Batches
- UC-04 Reserve Pickup Window
- UC-05 View Reservation & Verification Code
- UC-06 Mark Batch Expired
- UC-07 Send Nearby Shelter Notification

## UML Relationships
- UC-02 `<<include>>` UC-08 Validate Food Details
- UC-04 `<<include>>` UC-09 Verify Shelter Eligibility
- UC-07 `<<extend>>` UC-02 Post Surplus Food Batch
