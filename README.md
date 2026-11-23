# University Academic Advising Appointment System

## About This Project

For my Systems Analysis and Design course at Georgia Gwinnett College, I designed a University Academic Advising Appointment System using Visual Paradigm.

The goal of this project is to model a system that allows students to schedule appointments with academic advisors, while giving faculty advisors and department administrators the tools they need to manage the advising process.

This project focuses on the planning and design stages of software development, before building the actual application.

## How I Designed It

### 1. Identifying System Users and Requirements

I started by creating a UML Use Case Diagram in Visual Paradigm to identify who would use the system and what they needed to be able to do.

I identified three main users:

- **Students:** View available advisors and time slots, schedule appointments, and cancel or reschedule appointments.
- **Faculty Advisors:** Manage their availability, view scheduled appointments, and record advising notes.
- **Department Administrators:** Assign faculty advisors and generate advising reports.

After identifying the users, I added the different actions they could perform and connected them to their corresponding roles.

I also used UML relationships to show how certain actions connect. For example, scheduling an appointment includes viewing available time slots.

This helped me understand the system from the user's perspective before moving into the technical design.

**UML Use Case Diagram**

![University Academic Advising Use Case Diagram](screenshots/diagrams:use-case-diagram.png)

### 2. Creating the UML Class Diagram

After identifying the system users and their actions, I created a UML Class Diagram in Visual Paradigm to plan how the system would be organized.

I started with a `User` class for shared information like name, email, and authentication. Then I added `Student`, `Advisor`, and `Administrator` as separate classes that inherit from `User`. Each role has its own methods based on what that user needs to do in the system.

Next, I added classes for the information the system needs to manage, including appointments, advisor assignments, available time slots, recurring availability, and advising notes.

I connected the classes using associations and multiplicities to show how they relate. For example, one student can have multiple appointments, while each appointment belongs to one student. I also modeled how an appointment is linked to an availability slot to help prevent double-booking.

Finally, I added supporting classes such as `AppointmentController`, `SchedulingService`, `AppointmentRepository`, `NotificationService`, and `AuditEvent`. These helped me separate the appointment workflow from data storage, notifications, and activity tracking.

This part of the project helped me understand that a class diagram is more than a list of objects. I had to think about what each class is responsible for and how the different parts of the system would work together.

**UML Class Diagram**

![University Academic Advising Class Diagram](screenshots/class-diagram.png)

### 3. Creating the UML Sequence Diagram

*Documentation coming next.*

## What's Next?

I plan to build on these diagrams by developing a working application using Java or Python and a relational database.

**Project status:** System design and documentation in progress.
