## where to find them?

https://developers.sap.com/tutorial-navigator.html

BASICS: https://www.youtube.com/playlist?list=PLPVhB_hucPHx16aJKe325mX9y55xs-z67 (Blue Antoniette explaination)

#### CREATE A TABLE IN ECLIPSE 

https://developers.sap.com/tutorials/abap-environment-create-table..html
https://developers.sap.com/tutorials/abap-environment-rap100-generate-ui-service..html
### Create a ABAP Cockpit and a [[Booster]]

https://community.sap.com/t5/technology-blogs-by-sap/how-to-delete-and-recreate-your-sap-cloud-platform-trial-account/ba-p/13463508#comment-542391

https://developers.sap.com/tutorials/abap-environment-trial-onboarding..html

* If we create an object in ABAP (Eclipse), and need to delete it. Should follow the steps below: 

1. In Eclipse, Click on the **Transport Organizer** which is located at the right side
2. Search with your object in the Transport Organizer

![[Pasted image 20240809101727.png]]
** if there are more than one object, follow the steps below: 
Transport Organizer  --> Transport Request --> Right click in the Object --> Sort and Compress.

![[Pasted image 20240809113101.png]]

### Create a communication system in SAP
+ [[What is a communication system]]? 
https://developers.sap.com/tutorials/abap-custom-ui-bas-connect-s4hc.html

https://www.youtube.com/watch?v=Qk9A-VMo8R0
### Create an ABAP Cloud Project

https://developers.sap.com/tutorials/abap-environment-create-abap-cloud-project.html


### Create ABAP package, Database table and ABAP Class

https://developers.sap.com/tutorials/abap-environment-persistence.html

* It's important to activate, after it the icon will turn yellowish from white. 
![[Pasted image 20240805163547.png]]
### Create a SAP Fiori App and Deploy it to SAP S/4HANA Cloud, ABAP Environment

https://developers.sap.com/tutorials/abap-s4hanacloud-procurement-purchasereq-shop-ui..html


### Create Communication System to Connect to SAP BTP, ABAP Environment

Tenant: Use the customizing tenant

* how to install the ABAP Development Tools for Eclipse? https://www.youtube.com/watch?v=dJosT0kloJ0
+ Communication Management: Allow to establish secure communication between your solution and other systems. 
+ Communication Arrangements: help you to configure the electronic data exchange between the system and a communication partner.
Integrate the system between S/4HANA Cloud to connect to SAP BTB and [[ABAP Environment ]].

###  Create Service Consumption Model for Business Partner and Sales Order Item Cube

Tenant: Use the customizing tenant

Concept: Service consumption is the invocation of a service (Web service, application service, or enterprise service) by a service consumer. This is the logical next step after the iteration with ==the repository to determine the correct service to be invoked for a specific business context== (service discovery). 

* Creating destination with basic authentication: 

![[basica-authentication]]

------
To show the right tiles, you must to choose the right Catalog: 
![[Pasted image 20240729111020.png]]

For the "Custom CDS Views is "SAP_CORE_BC_EXT_CCV".

+ How to show CDS Views Tile: 
1) Go to the Indentity and Access Management to click in the tile: Maintain Business Roles.
![[Pasted image 20240729111844.png]]

2) Click on the Business Role that has access to the space: In this case "BR_DEVELOPER"

![[Pasted image 20240729112011.png]]

3) Click on the Business Catalogs and Edit. Here, we must add the catalog required for the specific tile "SAP_CORE_BC_EXT_CCV". After, just click on "Apply".

![[Pasted image 20240729112058.png]]

![[Pasted image 20240729112225.png]]

P.S.: If there is missing Catalog to have full access to the tile, SAP will automatically recommend another Catalog, so you must accept this recommendation. 

 4) Sing Out the account and enter again and Voilà!
 
![[Pasted image 20240729112522.png]]



