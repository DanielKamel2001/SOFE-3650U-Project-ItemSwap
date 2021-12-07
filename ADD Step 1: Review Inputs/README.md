| Category                        | Details                                                                                                                                                                                                                                                                                                                                                                            |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Design purpose                  | This is a greenfield system from a mature domain. The purpose is to produce a sufficiently detailed design to support the construction of the system.                                                                                                                                                                                                                              |
| Primary functional requirements | From the use cases presented, the primary ones were determined to be:

UC-4 Listing Creation

UC-6 View Listing

UC-7 Offer Creation

UC-8 View Received Offers                                                                                                                                                                                                                    |
| Quality attribute scenarios     | <br>

QA Scenario

Importance to customer

Difficulty of implementation

QA-1

Security 

High

High

QA-2

Usability

High

Low

QA-3

Scalability 

Medium

Medium

QA-4

Performance

Low

Low

QA-5

Performance

Medium

Medium

QA-6

Usability

Medium

Medium

QA-7

Security 

High

High

From this list, all are selected as drivers.                                   | QA Scenario | Importance to customer | Difficulty of implementation | QA-1

Security | High | High | QA-2

Usability | High | Low | QA-3

Scalability | Medium | Medium | QA-4

Performance | Low | Low | QA-5

Performance | Medium | Medium | QA-6

Usability | Medium | Medium | QA-7

Security | High | High |
| QA Scenario                     | Importance to customer                                                                                                                                                                                                                                                                                                                                                             | Difficulty of implementation |
| QA-1

Security                  | High                                                                                                                                                                                                                                                                                                                                                                               | High |
| QA-2

Usability                 | High                                                                                                                                                                                                                                                                                                                                                                               | Low |
| QA-3

Scalability               | Medium                                                                                                                                                                                                                                                                                                                                                                             | Medium |
| QA-4

Performance               | Low                                                                                                                                                                                                                                                                                                                                                                                | Low |
| QA-5

Performance               | Medium                                                                                                                                                                                                                                                                                                                                                                             | Medium |
| QA-6

Usability                 | Medium                                                                                                                                                                                                                                                                                                                                                                             | Medium |
| QA-7

Security                  | High                                                                                                                                                                                                                                                                                                                                                                               | High |
| Constraints                     | <br>

ID

Constraint

CON-1

A minimum of 4 simultaneous users must be supported

CON-2

The system must be accessed through a web browser on Windows 

CON-3

Listings are stored for a maximum of 30 days before being archived

CON-4

The server for the database must be generally reliable (Up when needed for demonstrations)

From this list, all are selected as drivers. | ID | Constraint | CON-1 | A minimum of 4 simultaneous users must be supported | CON-2 | The system must be accessed through a web browser on Windows | CON-3 | Listings are stored for a maximum of 30 days before being archived | CON-4 | The server for the database must be generally reliable (Up when needed for demonstrations) |
| ID                              | Constraint                                                                                                                                                                                                                                                                                                                                                                         |
| CON-1                           | A minimum of 4 simultaneous users must be supported                                                                                                                                                                                                                                                                                                                                |
| CON-2                           | The system must be accessed through a web browser on Windows                                                                                                                                                                                                                                                                                                                       |
| CON-3                           | Listings are stored for a maximum of 30 days before being archived                                                                                                                                                                                                                                                                                                                 |
| CON-4                           | The server for the database must be generally reliable (Up when needed for demonstrations)                                                                                                                                                                                                                                                                                         |
| Architectural concerns          | As this is a greenfield system, a select few architectural concerns are identified:

CRN-1: Leverage existing code and team’s knowledge to expand and improve existing structure.

CRN-2: Modify existing structure to implement architectural structures and design patterns

CRN-3: Allocate work to all members of the development team.                                        |
