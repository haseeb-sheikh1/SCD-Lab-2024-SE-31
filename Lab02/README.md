# Lab 2: Activity and State Machine Diagrams

**Modelling the foodPanda, Toaster and Elevator systems in UML**

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

Practise two UML behavioural diagrams: the **activity diagram**, which shows how work flows between people or systems, and the **state machine diagram**, which shows how one object changes state in response to events.

## Tasks

| Task | System | Diagram type | Key idea |
|------|--------|--------------|----------|
| Q1 | foodPanda ordering | Activity diagram with swimlanes | Who does what, and in what order |
| Q2 | Toaster | State machine | Activities inside states; triggered and triggerless events |
| Q3 | Elevator / Lift | State machine | Movement, doors and safety states |

## Method

The same four-stage routine was used for every diagram:

1. **Understand the system:** describe it in one sentence and list who or what is involved.
2. **Identify the building blocks:** actions (activity diagram) or states and events (state machine).
3. **Draw in Visual Paradigm:** add the initial node, place elements, connect with labelled arrows.
4. **Check and refine:** every path starts at the initial node, every state is reachable, every arrow is labelled.

---

## Task 1: foodPanda Activity Diagram

Three swimlanes (**Customer**, **Restaurant**, **Rider**) show which participant is responsible for each step. An arrow crossing a lane boundary is a hand-over.

| Lane | Action | What happens |
|------|--------|--------------|
| Customer | Browse Menu & Order | Customer picks items and places the order |
| Restaurant | Accept & Prepare Order | Restaurant confirms and cooks the order |
| Rider | Pick Up Order | Rider collects the food from the restaurant |
| Rider | Deliver Order | Rider hands the food to the customer; process ends |

## Task 2: Toaster State Machine

**States:** Idle, Toasting, Jammed.

| State | Entry | Do | Exit |
|-------|-------|----|------|
| Idle | None | Waits for user input | None |
| Toasting | Turn on heater | Apply heat to bread | Turn off heater |
| Jammed | None | Waits for obstruction to be cleared | None |

| From | To | Label | Type |
|------|----|-------|------|
| Idle | Idle | Turn browning dial / update timer duration | Triggered |
| Idle | Toasting | Lever pushed down | Triggered |
| Toasting | Idle | Toast pops up | Triggerless (fires when toasting completes) |
| Toasting | Idle | Cancel button pressed | Triggered |
| Toasting | Jammed | Mechanism stuck | Triggered |
| Jammed | Toasting | User clears obstruction | Triggered |

Because *Toasting* has an exit action, the heater is switched off on every path out of the state (pop-up, cancel or jam). The safety behaviour is written once and applies everywhere.

## Task 3: Elevator State Machine

**States:** Idle, Moving Up, Moving Down, Stationary (doors open), Overloaded.

| From | To | Event / action |
|------|----|----------------|
| Idle | Moving Up | Floor button pressed (higher) |
| Idle | Moving Down | Floor button pressed (lower) |
| Moving Up | Stationary | Target floor reached / open doors |
| Moving Down | Stationary | Target floor reached / open doors |
| Stationary | Idle | Timer expires / close doors |
| Stationary | Overloaded | Weight limit exceeded |
| Overloaded | Stationary | Weight reduced below limit |

The lift can only enter *Overloaded* from *Stationary*, so it never starts moving while overweight.

---

## Key Takeaways

- Swimlanes make responsibility and hand-overs visible at a glance.
- Entry/do/exit activities and the triggered vs. triggerless distinction clarify object behaviour.
- A safety condition (overload) can be modelled as its own state.

## Folder Contents

```
Lab-2-Activity-and-State-Machine-Diagrams/
├── README.md
├── Lab-2-Report-2024-SE-31.pdf     # Full lab report
└── diagrams/                       # Exported diagram images (optional)
    ├── foodpanda-activity.png
    ├── toaster-state-machine.png
    └── elevator-state-machine.png
```
