# Lab 1: Use Case Diagrams

**Modelling the Online Ticket Reservation System and Credit Card Processing System in UML**

| | |
|---|---|
| **Course** | Software Construction & Development (Lab), SE-3102 |
| **Instructor** | Engr. Dr. Asma Javaid |
| **Department** | Software Engineering, University of Azad Jammu and Kashmir (UAJK) |
| **Semester** | Fall 2026 |
| **Submitted by** | Sheikh Haseeb-ur-Rehman (2024-SE-31) |
| **Date** | October 26, 2026 |
| **Tool** | Visual Paradigm Community Edition |

---

## Objective

Practise use case modelling and requirements analysis by identifying actors, defining system boundaries, drawing UML use case diagrams, and writing a detailed specification for one key use case in each system.

## Tasks

| Task | System | Interaction | Diagram |
|------|--------|-------------|---------|
| 1 | Online Ticket Reservation System | Web user interface | UML use case diagram |
| 2 | Credit Card Processing System (POS) | POS terminal hardware | UML use case diagram |

---

## Task 1: Online Ticket Reservation System

**Actors**
- **Customer (primary):** browses schedules, selects seats and pays online.
- **System Admin (secondary):** manages cancellations and releases seat inventory.

**Use cases:** Search Ticket, Book Ticket, Process Payment, Cancel Booking.

**Specification: UC-01 Book Ticket**

| Field | Details |
|-------|---------|
| Primary actor | Customer |
| Pre-conditions | Customer has searched for tickets and selected a seat |
| Main flow | 1. Customer selects ticket and clicks *Book Ticket*<br>2. System locks seat inventory for 10 minutes<br>3. Customer confirms payment details |
| Post-conditions | Booking record status set to *Pending Payment* |
| Exceptions | Seat booked concurrently: system prompts re-selection |

## Task 2: Credit Card Processing System

**Actors**
- **Customer (primary):** selects items, swipes the card, signs the receipt.
- **Vendor (operational):** generates the bill and hands over printed balance statements.
- **Card Reader (hardware):** reads card data, contacts the bank server, prints statements.

**Use cases:** Select Item, Swap Card, Generate Bill, Process Amount Transaction, Issue Balance Statement, Sign Receipt.

**Specification: UC-02 Process Amount Transaction**

| Field | Details |
|-------|---------|
| Primary actors | Card Reader (hardware), Vendor, Customer |
| Pre-conditions | Card swiped in POS terminal; total bill calculated by Vendor |
| Main flow | 1. Card reader reads card data and sends bank authorization<br>2. Bank validates limit and approves the amount<br>3. Balance decremented and confirmation returned |
| Post-conditions | Transaction completed and merchant account credited |
| Exceptions | Insufficient balance: card reader displays *Declined* |

---

## Key Takeaways

- **Interaction differs:** Task 1 is driven by a web UI; Task 2 by physical POS hardware.
- **Validation differs:** ticket booking uses temporary seat holds (asynchronous), while card processing needs real-time synchronous bank verification.
- Both human and hardware actors were identified, and core flows were captured in concise specifications.

## Folder Contents

```
Lab-1-Use-Case-Diagrams/
├── README.md
├── Lab-1-Report-2024-SE-31.pdf     # Full lab report
└── diagrams/                       # Exported diagram images (optional)
    ├── ticket-reservation-use-case.png
    └── credit-card-use-case.png
```

## Viewing the Diagrams

The source diagrams were created in Visual Paradigm Community Edition. Open the report PDF to see them in context, or export them from the project file if you include it.
