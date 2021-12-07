# SOFE-3650U-Project-ItemSwap (SwapThing)
_Group 23: Adris Azimi, Abida Choudhury, Daniel Gohara Kamel, Jessica Leishman_
----
This is a repository of for the SOFE 3650U term project. It works off of a previous assignment and expands the focus on architecture for the SOFE 3650U course. The files related to the previous courses can be found here:  https://github.com/jessica-leishman/Group68_ItemSwap 

----
# Table of Contents
- ### Project Proposal
  - [Project Overview](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap#project-overview)
  - [Inital Draft](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/Proposal/SOFE%203650U%20Proposal%20(ItemSwap).pdf)
  - [Revision: November 6, 2021](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/Proposal/SOFE%203650U%20Proposal%20Nov82021.pdf)
- ### Progress Report: November 8, 2021
  - [Summary of Deliverables](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap#progress-report-summary-of-deliverables)
  - [Use Case Diagram]()
  - [Use Case Descriptions](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/Use%20Cases/Use%20Case%20Descriptions.pdf)
  - [Quality Attributes](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/Quality%20Attributes%20and%20Constraints/QA%20and%20Associated%20Use%20Cases.pdf)
  - [Constraints](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/Quality%20Attributes%20and%20Constraints/Constraints.pdf)

- ### Attribute- Driven Design Process (ADD) 
  - #### [ADD Step 1](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%201/ADD%20Step%201.pdf)
    - [Iteration 1 Step 1 PDF](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%201/ADD%20Step%201.pdf)
  - #### [Iteration 1](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/tree/main/ADD%20Iteration%201)
    - [Iteration 1 Report PDF](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%201/ADD%20Iteration%201%20Report%20pdf.pdf)
    - [System Context Diagram](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%201/Context%20Diagram.png)
    - [Component View Diagram](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%201/Component%20View%20Diagram.png)
    - [Initial Deployment Diagram](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%201/Initial%20Deployment.png)
  - #### [Iteration 2](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/tree/main/ADD%20Iteration%202)
    - [Iteration 2 Report PDF](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%202/ADD%20Iteration%202%20Report%20pdf.pdf)
    - [Revised Component View Diagram from Iteration 1](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%202/Revised%20Component%20view%20Diagram.png)
    - [Domain Model of Entities](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%202/Domain%20Model%20of%20entities.png)
    - [Entity Use Case Relations](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%202/Entities%20relations%20to%20usecases%20and%20data%20stores.png)
  - #### [Iteration 3](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/tree/main/ADD%20Iteration%203)
    - [Iteration 3 Report PDF](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%203/ADD%20Iteration%203%20Report%20pdf.pdf)
    - [Revised Deployment Diagram](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%203/Revised%20Deployment%20Diagram.png)
    - [QA-4 Sequence Diagram](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/ADD%20Iteration%203/QA4%20Sequence%20Diagram.png)
 
 ----

## Project Overview
 This project will be an Item-Swap and Bartering website.  Users will be able to create an account to make a profile and create listings for an item.  They will be able to browse and search other listings and make offers on those listings. Offers can include items and money.  The listing will have a picture uploaded by the user, requested offers (items/money or both), and a description of the item.  The listing page will also include a link to the posting user’s profile.

This website will showcase HTML, CSS, JavasScript, and PHP. The website will also incorporate the use of a mySQL database for the creation, maintenance, and storage of data.


## Progress Report Summary of Deliverables
### Use Case Diagram
![Use case diagram for item swapping system](https://github.com/DanielKamel2001/SOFE-3650U-Project-ItemSwap/blob/main/Use%20Cases/Use%20Case%20Diagram.png)

### Use Case Descriptions
 ID | Title | Description 
:-----:|:----:|:----:
UC-1 | Create Account | A user submits their information (username, email, password) which is stored in the database if unique
UC-2 | Log in | A user logs into the system through a login/password screen. Upon successful login, the user is presented with different options according to their role. 
UC-3 | Manage users |Admin can delete other users listings and offers/messages if necessary, Admin can also grant other accounts admin status
UC-4 | Listing Creation | A user that is logged into an account can create a listing along with a picture and a description that are stored in the database.
UC-5 | Listing Modification | When logged in, a user can edit or delete their own listings.
UC-6 | View Listing | Displays the title, description, and image of a listing. If the listing belongs to the user who is logged in, allow the user to edit.
UC-7 | Offer Creation |When logged in, a user can place offers on other users listings
UC-8 | View Received Offers | When logged in, a user can see offers other users have placed on their own listings. Other users can not see offers placed on the listing
UC-9 | View Sent Offers | When logged in, a user’s offers they have made on other user’s listings are viewable from the “View Sent Offers” page.
UC-10 | Delete Sent Offers  | When logged in, a user can delete the offers they have sent from the “View Sent Offers” page.
UC-11 | Delete Received Offers  | When logged in a user can delete received offers on their listings.
UC-12 | Send Offers | When logged in, a user can send offers on listings of other items.
UC-13 | Search Listings | A user enters the item that they are searching for then the system queries the database for listings with titles that contain the query 
UC-14 | View Self Profile | When logged in, a user can view their own profile fetched from the local data cache.
UC-15 | View Other Profile | When logged in, a user can view the profiles of others fetched from the database.

### Quality Attributes and Associated Use Cases
ID | Quality Attribute | Scenario | Associated Use Case(s)
:----:|:----:|:----:|:----:
QA-1 | Security | A general or administrator  visits the site. They are not able to view the passwords of other users. | UC-2, UC-1
QA-2 | Usability | A user accesses the site. The navigation bar is clearly indicated, the colour scheme does not cause eye strain, and the webpages utilize accessible web design. | All
QA-3 | Scalability | Site is able to handle multiple users (min. 4) with little to no decrease in service quality | All
QA-4 | Performance | A user accesses the main homepage of the website.  The page and listings to the site are sent to the user within 30 seconds | UC-2, All
QA-5 | Performance | A user (A) sends an offer to another user (B). B is able to quickly (within the hour if so desired) and descriptively respond to A’s offer.  | UC-6, UC-7
QA-6 | Usability | A user (A) sends an offer to another user (B). The UI for B to respond is intuitive and clearly labeled. | UC-6, UC-7
QA-7 | Security | A user (A) sends an offer to another user (B). Users outside of A and B cannot view the offer sent in any form. | UC-6, UC-7

### Constraints
ID | Constraint |Associated Use Case(s)
:----:|:----:|:----:
CON-1 | A minimum of 4 simultaneous users must be supported | All
CON-2 | The system must be accessed through a web browser on Windows | All
CON-3 | Listings are stored for a maximum of 30 days before being archived | All
CON-4 | The server for the database must be generally reliable (Up when needed for demonstrations) | All







