# Attribute-Driven Design (ADD) Iteration 2 for SwapThing System
In this iteration, decisions that determine the methods used for implementation and the development teams are made here.  Concrete decisions regarding location of components, implementation technologies, and some reasoning regarding the interfaces which are required by the various components.

## Iteration 2 Quick Links:
- ### [Use Case Descriptions](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/Use%20Cases/Use%20Case%20Descriptions.pdf)
- ### [Quality Attributes](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/Quality%20Attributes%20and%20Constraints/QA%20and%20Associated%20Use%20Cases.pdf)
- ### [Iteration 2 Report PDF](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%202/ADD%20Iteration%202%20Report%20pdf.pdf)
   - #### [Step 2. Establish Iteration Goal by Selecting Drivers](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/tree/main/ADD%20Iteration%202#step-2-establish-iteration-goal-by-selecting-drivers-1)
   - #### [Step 3. Choose One or More Elements of the System to Refine](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/tree/main/ADD%20Iteration%202#step-3-choose-one-or-more-elements-of-the-system-to-refine-1)
   - #### [Step 4. Choose One or More Design Concepts That Satisfy the Selected Drivers](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/tree/main/ADD%20Iteration%202#step-4-choose-one-or-more-design-concepts-that-satisfy-the-selected-drivers-1)
   - #### [Step 5. Instantiate Architectural Elements, Allocate Responsibilities, Define Interfaces:](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/tree/main/ADD%20Iteration%202#step-5-instantiate-architectural-elements-allocate-responsibilities-define-interfaces-1)
   - #### [Step 6. Sketch Views and Record Design Decisions:](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/tree/main/ADD%20Iteration%202#step-6-sketch-views-and-record-design-decisions-1)
      - [Revised Component View Diagram from Iteration 1](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%202/Revised%20Component%20view%20Diagram.png)
      - [Domain Model of Entities](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%202/Domain%20Model%20of%20entities.png)
      - [Entity Use Case Relations](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%202/Entities%20relations%20to%20usecases%20and%20data%20stores.png)
   - #### [Step 7. Perform Analysis of Current Design and Review Iteration Goal and Achievement of Design Purpose](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/tree/main/ADD%20Iteration%202#step-7-perform-analysis-of-current-design-and-review-iteration-goal-and-achievement-of-design-purpose-1)

<br><br>

## Step 2. Establish Iteration Goal by Selecting Drivers
For this iteration, a few primary use cases were selected as the driving forces for system decisions:

- _**UC-4, Listing Creation**_
- _**UC-6, View Listing**_
- UC-7, Offer Creation
- UC-8, View Received Offers
<br>

## Step 3. Choose One or More Elements of the System to Refine
The elements of the system chosen to be refined for this iteration are the various components needed to execute each of the use cases described in step 2, however, emphasis is placed on the components needed to achieve the basic functionality of the site: viewing and posting items.

- Browser/UI
- _**Generate Page**_
- _**Request Page**_
- _**Request Data**_
- Modify Data
- Data Access
- Validate login/current user
<br>

## Step 4. Choose One or More Design Concepts That Satisfy the Selected Drivers
Some design concepts were selected to help fulfill the primary use cases and begin identifying the various domain objects and their relationships to help further guide implementation and modelling.

Design Decisions and Location| Rationale and Assumptions
--- | ---
Identify domain objects that relate to corresponding use cases | Domain objects are Listings, Users, and Offers.  Pages interact with these objects to implement functionality. Functionality referring to viewing, creating, or modifying these objects
Create Domain Model (website map of sorts) to show where domain objects interact within the system | A domain model must be created to indicate where objects interact with the various navigation pages, which act as generators based on the object information passed to the ViewPage component. Must create a domain model, as without it functionality and architecture will not be clearly defined, resulting in a design that cannot easily be followed and maintained.
Construct modules/components from decomposed domain objects (identify key functionality and groupings/units)|Objects and pages must be grouped based on where they lie within the layered architecture. This is to create specialized components based on required functionality.
<br>

## Step 5. Instantiate Architectural Elements, Allocate Responsibilities, Define Interfaces
Functionality is allocated to the various components, and decisions regarding the interaction processes and responsibilities of each element is outlined in the table below.  Some preliminary decisions regarding implementation technology are made during this step as well

Design Decisions and Location|Rationale
---|---
Create basic domain model with focus on interactions and components|Objects interact with various pages of the system to generate different content based on the navigation page selected by the user.  Only a simple domain model is to created to expedite this part of the development process, as there are not many objects given the nature of the system
Objects will be stored as tuples in tables in a MySQL database|Some pages will need several specific objects to create them so they need to queryable. <br>  Objects includes:<br>Listings (ID, Title, Description, PostingUser) Users (ID, Username, password) Offers (ID, PostingUserID, RecivingListing ID, Description, ContactDetails)<br><br> ViewPage(input listings, user profile, or Offers to generate a page to display them) -> function associated with several of the objects, varies depending on page attempting to be generated
Several relevant object instances will be stored in the Local Data Cache as a JSON string. Only necessary and displayable information is stored.|Some pages require object information where the objects they may need are a smaller subset rather than the whole dataset.<br>These objects can be predicted, such as all listings belonging to a specific user needed for easy loading from that user's profile, or the most recent/popular listings to be displayed on the homepage for quick traversal back and forth from those listings and the home page.<br>These predicted objects will be queried from the database and stored as a Json string on the user client. When a page request is sent, the string timestamp is sent alongside to check whether new information should be queried and sent or if the existing information in the local cache store is valid for page generation.<br>Preventing the database to be queried several times for similar queries and over reliance on the server.
Pages will be generated using PHP|PHP offers built-in methods to access a MySQL database and support for extracting information from those tuples into associative arrays alongside Json string decoding into the same array format. So the same code to generate pages can be used for both the local data and database server data.
<br>

## Step 6. Sketch Views and Record Design Decisions
![Revised Component View Diagram from It. 1](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%202/Revised%20Component%20view%20Diagram.png)

_Figure 4: Revised system diagram from iteration 1. This revised diagram shows the implementation of a local data cache and the relocation of the Request Page component. Upon page generation the local cache is updated with listings and other information required to display listings and the homepage. When a page is requested through the Request Page component, the Generate page component chooses to generate the page either by using the local data cache it was sent or by interacting with a lower layer to access the database server._
<br>

![Domain model of entities](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%202/Domain%20Model%20of%20entities.png)

_Figure 5 : Displays three kinds of entities that will be used in the system._

<br>

![Entity Usecase relations](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%202/Entities%20relations%20to%20usecases%20and%20data%20stores.png)

_Figure 6 : This diagram shows the relations of the different domain objects to use cases and where those use cases would retrieve the needed objects from._
<br>

## Step 7. Perform Analysis of Current Design and Review Iteration Goal and Achievement of Design Purpose
The focus of this iteration were several of the primary use cases. Numerous design decisions regarding implementation technology and component locations were made to support them.  

The use cases or quality attributes which no longer require further refinement are stored within the “Completely Addressed” column.  Anything “Partially Addressed” should be revisited in further iterations to complete the system design to the required level of detail.

Not Addressed|Partially Addressed|Completely Addressed|Design Decisions Made During Iteration
---|---|---|---
|</br> |</br> |QA-6|Create basic domain model with focus on interactions and components
|</br> |</br>|UC-7,<br>UC-4,<br>UC-15|Objects will be stored as tuples in tables in a MySQL database
|</br>  |QA-1|QA-4,<br>UC-6,<br>UC-14|Relevant objects stored as a Json string in a local data cache.
| </br> |QA-4|UC-6,<br>UC-8|Pages will be generated using PHP

_**Quality Attributes, Constraints not addressed/applicable in this iteration:**_
QA-3, QA-7, CON-1, CON-3
<br>

The focus of this iteration were the use cases and implementing a system to clarify components behaviour in them. Design decisions were made to support this goal. Notably UC 14 was influenced in the introduction of the local data cache to store context relevant listings so that the main database server is not constantly queried with redundant searches.