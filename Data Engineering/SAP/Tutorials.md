## where to find them?

https://developers.sap.com/tutorial-navigator.html

### Create Communication System to Connect to SAP BTP, ABAP Environment

* how to install the ABAP Development Tools for Eclipse? https://www.youtube.com/watch?v=dJosT0kloJ0
+ Communication Management: Allow to establish secure communication between your solution and other systems. 
+ Communication Arrangements: help you to configure the electronic data exchange between the system and a communication partner.
Integrate the system between S/4HANA Cloud to connect to SAP BTB and [[ABAP Environment ]].

###  Create Service Consumption Model for Business Partner and Sales Order Item Cube

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