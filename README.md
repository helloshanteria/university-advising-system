# University Academic Advising Appointment System

**Systems Analysis & Design | Georgia Gwinnett College**

## Project Overview

For my Systems Analysis and Design course at Georgia Gwinnett College, I designed a University Academic Advising Appointment System to explore how technology can improve the coordination of academic advising.

Rather than jumping straight into development, I started by looking at the business side of the system. I wanted to understand who would use it, what each user needed to accomplish, and how the system could support their daily responsibilities.

From there, I translated those requirements into three UML diagrams that represent the system's functionality, structure, and behavior.

**Tools:** Visual Paradigm, UML

**Skills Applied:** Business Requirements Analysis, Systems Analysis and Design, Business Process Modeling, Object-Oriented Design, System Architecture, Technical Documentation, and Software Development Life Cycle (SDLC)

**Project Status:** System Design Phase — UML diagrams completed; application development planned.

## Understanding the Business Problem

Academic advising requires coordination between students, faculty advisors, and department administrators. Without a centralized scheduling process, managing appointments, communicating availability, and maintaining consistent records could become challenging.

When approaching this project, I considered several questions:

- How can students easily identify their assigned advisor and schedule an appointment?
- How can advisors manage their availability and prevent scheduling conflicts?
- How can administrators maintain visibility into advising assignments and appointment activity?
- How can the system maintain accurate and consistent information?

These questions helped me establish the purpose of the system before determining how it should be designed.

*This project is based on a hypothetical university scenario developed for coursework.*

## Business Requirements

I identified three primary stakeholders and the functionality each would need from the system.

| Stakeholder | Business Needs |
|---|---|
| Students | View assigned advisors, check availability, schedule, reschedule, and cancel appointments. |
| Faculty Advisors | Manage availability, view scheduled appointments, and record advising notes. |
| Department Administrators | Assign advisors to students, review advisor assignments, and generate appointment reports. |

Beyond individual user needs, I also considered business rules such as preventing double bookings, supporting virtual and in-person appointments, maintaining appointment records, and communicating scheduling outcomes.

## Translating Business Requirements into System Design

### 1. UML Use Case Diagram — Understanding User Needs

I started with a use case diagram to identify how each stakeholder would interact with the system.

This allowed me to establish the scope of the application and determine which functions were necessary to support each user's responsibilities.

For example, before a student can schedule an appointment, they need access to their assigned advisor and available time slots. Understanding these relationships helped me identify the functionality required before designing the system's internal structure.

![University Academic Advising Use Case Diagram](screenshots/diagrams:use-case-diagram.png)

### 2. UML Class Diagram — Designing the System Structure

After identifying the functional requirements, I created a class diagram to organize the information, operations, and relationships within the system.

I applied object-oriented design principles by creating a shared `User` class with three specialized classes: `Student`, `Advisor`, and `Administrator`.

I also modeled relationships between appointments, advisor assignments, availability slots, and advising notes.

One of the more challenging parts of this process was determining how these classes should relate to one another while supporting the business requirements.

To keep responsibilities organized, I introduced several supporting components:

| Component | Responsibility |
|---|---|
| AppointmentController | Receives appointment requests. |
| SchedulingService | Manages scheduling logic and conflict checks. |
| AppointmentRepository | Provides access to appointment records. |
| NotificationService | Supports appointment confirmations and reminders. |
| AuditEvent | Records system activity. |

Designing these components helped me understand the importance of separating responsibilities and organizing a system in a way that could support future development.

![University Academic Advising Class Diagram](screenshots/class-diagram.png)

### 3. UML Sequence Diagram — Modeling the Appointment Workflow

The sequence diagram allowed me to take the structure I designed and demonstrate how the different components would work together when a student requests an appointment.

I modeled two possible scheduling outcomes:

**Successful Appointment**

- Verify availability and check for scheduling conflicts.
- Generate a meeting link if the appointment is virtual.
- Reserve the selected time slot.
- Save the appointment record.
- Send an appointment confirmation.
- Record the scheduling activity.

**Unsuccessful Appointment**

- Identify an unavailable time slot or scheduling conflict.
- Reject the appointment request.
- Communicate the outcome to the student without creating an appointment.

I used an alternative (`alt`) fragment to represent the two scheduling outcomes and an optional (`opt`) fragment to handle virtual meeting link creation.

![University Academic Advising Sequence Diagram](screenshots/University_Student_Advising_Student.png)

## Connecting Business Requirements to Technical Solutions

An important part of this project was understanding how individual technical operations support larger business objectives.

| Business Requirement | Technical Solution |
|---|---|
| Prevent scheduling conflicts | `checkConflicts()`, `isAvailable()`, and `blockSlot()` |
| Support virtual advising | `createMeetingLink()` |
| Maintain appointment records | `AppointmentRepository.save()` |
| Improve communication | `NotificationService.sendConfirmation()` |
| Support accountability | `AuditEvent.recordEvent()` |

I also considered data integrity during the scheduling process. In a working application, reserving a time slot and saving the appointment would need to occur within an atomic transaction to help prevent double bookings and inconsistent records.

## Expected Business Value

If developed and implemented, this system could support a university by:

- Reducing scheduling conflicts and administrative workload.
- Making academic advising more accessible to students.
- Improving visibility into advisor availability.
- Supporting consistent appointment and advising records.
- Providing administrators with information for reporting and decision-making.

These are anticipated benefits of the proposed design rather than measured results from an implemented application.

## What I Learned

Before working on this project, I primarily associated application development with programming. This experience helped me understand how much planning and decision-making take place before development begins.

I learned how to evaluate a business problem, identify stakeholder needs, establish functional requirements, and translate those requirements into a technical design.

It also helped me understand how object-oriented programming concepts, business rules, data relationships, and system architecture work together to support a larger business objective.

As an Information Technology student concentrating in Data Science and Analytics, I found this especially valuable because the way a system is designed can directly influence the quality, accessibility, and usefulness of the data it produces.

## What's Next

Now that I've completed the system design, my next goal is to turn this project into a functional application using Python or Java and a relational database.

I'm looking forward to applying what I've learned in my programming, database, and systems analysis courses to develop the features I've designed, including appointment scheduling, availability management, conflict prevention, and notifications.

I also want to explore how appointment data can be used for reporting and analytics to support administrative decision-making.

Continuing this project will give me the opportunity to strengthen my technical skills while gaining a better understanding of how a business problem evolves from initial requirements and system design into a working application.

---

**Shanteria Johnson**

B.S. Information Technology — Data Science & Analytics

Georgia Gwinnett College
