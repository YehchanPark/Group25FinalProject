# Iteration 1 : Establishing an Overall System Structure
This iteration showcases the results of the activites that are performed for the first iteration of the add process. The goal of this iteration is to establish an overall system structure.

To access to full pdf click [here](Iteration%201%20Final%20Project%20SOFE3650.pdf)

## **ADD Step 1: Review inputs**


|**Category**|**Details**|
| :- | :- |
|Design Purpose|<p>This is a greenfield system from a mature domain. The purpose</p><p>is to create a sufficient design to support the</p><p>construction of the system. </p>|
|Primary Functional Requirements|<p>From the use cases presented in Deliverable 2, the primary ones were determined to be:</p><p></p><p>- UC-1: Because it directly supports the core business</p><p>- UC-4: Because it directly supports the core business </p><p>- UC-6: Because it directly supports the core business</p><p>- UC-7 Because it grants the ability to troubleshoot and modify in real time</p>|
|Quality Attribute Scenarios|<p>The scenarios were described in Deliverable 2. They have now</p><p>been prioritized as follows:</p>|

|**Scenario ID**|**Importance to Customers**|**Difficulty of Implementation according to architect**|
| :- | :- | :- |
|QA-1|High|Medium|
|QA-2|Medium|Medium|
|QA-3|Low|Low|
|QA-4|High|Medium|
|QA-5|Medium|Medium|
|QA-6|Low|Low|
|QA-7|High|High|
|QA-8|High|High|
|QA-9|Medium|Low|

||From this list quality attributes 1, 4, 7, and 8 are selected as drivers.|
| :- | :- |
|Constraints|All the constraints discussed in the second deliverable are included as drivers.|
|Architectural Concerns||

|ID|Concern|
| :- | :- |
|CRN-1|Establishing an overall initial system structure.|
|CRN-2|Leverage the team's knowledge about Web Programming, including HTML, CSS, Javascript, PHP, SQL and AJAX . |
|CRN-3|Allocate work to members of the development team.|


## **Step 2: Establish Iteration Goal by Selecting Drivers**

This is the first iteration in the design of a greenfield system, so the iteration goal
is to achieve the first architectural concern of establishing an overall system structure .
Although this iteration is driven by a general architectural concern, the architect must keep in mind all of the drivers that may influence the general structure of the system. In particular, the architect must be mindful of the following:

QA-1: Security

QA-4: Performance, Availability

QA-7: Security

QA-8: Security

CON-2: User workstations use the following operating systems: Windows and Linux.

CON-4: Must use the theatre's existing databases.

CON-5: The system must be accessed through a web browser such as Chrome or Firefox while on different operating systems.

CRN-2: Leverage the team's knowledge about Web technologies, including HTML, CSS, Javascript, PHP, SQL and AJAX . 

Context Diagram for the theatre reservation system:  
![Context Diagram](assets/context%20diagram.PNG)


## **Step 3: Choose One or More Elements of the System to Refine**

Our system is a greenfield system, so the element to refine is the entire theatre reservation system, which is shown in the diagram above. Refinement is performed through decomposition.

## **Step 4: Choose One or More Design Concepts That Satisfy the Selected Drivers**

|**Design decisions and Location**|**Rationale**|
| :- | :- |
|Theatre Reservation System will be structured using the **Rich Internet Application** reference architecture|The Rich Internet Application reference architecture supports the development of applications that utilize a rich user interface and runs inside a web browser.  This type of application supports business logic on the client side which allows a responsive exchange of information between the client and server part of the system.  This advantage is especially useful in achieving QA-4, where data is required to be updated/retrieved quickly.  Constraint 5 is also satisfied with the Rich Internet Application, as it allows the system to be accessed through the user's choice of web browser.|
||<p>**Discarded alternatives:**</p><p></p>|

|**Alternative**|**Reason for discarding** |
| :- | :- |
|Web Application|While the design does include a very mobile and web based option, it does have limitations for what it can accomplish. This design concept was ultimately discarded due to the difficulty of implementing a rich user interface.|
|Rich Client Application|This architecture is designed to be highly responsive by running on the users’ machines. The design was discarded as the desired system requires high network connectivity and does not want to heavily use the user’s machine resources.|
|Mobile Applications|This architecture is focused toward the development of applications that are to be deployed on mobile devices. This alternative was discarded because mobile devices were not considered for accessing this system.|

|||
| :- | :- |
|<p>Physically structure</p><p>the application</p><p>using the **three-tier**</p><p>**deployment** **pattern**</p>|Since the system will be accessed from a web browser (CON-5) and the theatre's existing database must also be used (CON-4), a three tier deployment is appropriate.  Includes the presentation tier, application tier, and data tier. |
|Build the user interface of the client using HTML and other **web technologies** |<p>The standard for building web applications ensures proper compatibility ( CON-5) and it is what the developers are already familiar with (CRN-2).</p><p>Discarded Alternatives: Java servlets were considered , but the developers understanding of the technologies was not sufficient enough. </p>|



## **Step 5: Instantiate Architectural Elements, Allocate Responsibilities, and Define Interfaces**

In the initial iteration, interfaces are not yet defined. 

|**Design Decision and Location**|**Rationale**|
| :- | :- |
|Remove local data sources in the Rich Internet Application|No need to store data locally as information will be stored in the Theatre Database.|


## **Step 6: Sketch Views and Record Design Decisions**  
![view](assets/sketch.PNG)  
The following table summarizes the information that is captured by the sketch : 
|**Element**|**Responsibility**|
| :- | :- |
|Browser Layer|This layer contains the canvas for user interaction and use case control flow.  Will use HTML and CSS to implement. |
|Service Interface|Various service components are utilized by the end users.|
|Business Layer|This layer contains the modules that perform the business logic operations.  This can be carried out on the server side.|
|Data Layer|This layer houses the components needed to communicate with the theatre server. |
|Cross Cutting|This extra hidden layer contains the website's security, operational management, and communication with the theatre database server.  The service, business, and data layer all make use of this helpful layer. |
|Rich UI Engine|This highly interactive user interface will make the software feel more responsive to the end user.|
|Business Processing Component|Element will send and receive delicate information from the client and server sides.|
|Message Types|Contains the appropriate class of variable to send or receive.|
|Business Components |Incorporate business operations  that require processing on the server side. |
|Business Entities|These entities make up the domain model. |
|Access Module|Retrieves data from theatre database.|
|Data Utilities|Tools in order to retrieve and collect data. Used in the business layer. |



Deployment Diagram:  
![Deploment Diagram](assets/deployment%20diagram.PNG)  
The responsibilities of the elements are:


|**Element**|**Responsibility** |
| :- | :- |
|User Device|The device (most likely a pc), which houses the client side logic part of the program|
|Application Server|The server that host the server side logic of the program, it also serves the web pages|
|Database Server|Server that hosts the the relational database|
The relationship between elements:

|**Relationship**|**Description**|
| :- | :- |
|Between application and database server|Communication with the database will be done using PHP.|

## **Step 7: Perform Analysis of Current Design and Review Iteration**


|**Not Addressed**|**Partially Addressed**|**Completely Addressed**|**Design Decisions** |
| :- | :- | :- | :- |
||UC-1||Selected reference architecture establishes the modules that will support this functionality.|
||UC-4|||
||UC-6|||
||UC-7|||
||QA-4||Introduced business logic module on the client side to provide fast and secure data transfer. |
|||CON-5|Use of the Rich Internet Application being programmed in Java, which supports the website across different browsers and operating systems.|
||QA-1||Selected relevant drivers.|
||QA-4|||
||QA-7|||
||QA-8|||
|||CRN-2|Leverage the team's knowledge about Web technologies, including HTML, CSS, Javascript, PHP, SQL and AJAX . |
||CON-2||Took into account the following elements, mindful while deciding project drivers. |
||CON-4|||
|UC-2|||No relevant decisions made, elements did not fit this iterations scenario. |
|UC-3||||
|UC-5||||
|UC-8||||
|QA-2||||
|QA-3||||
|QA-5||||
|QA-6||||
|QA-9||||
|CON-1||||
|CON-3||||
|CON-6||||

