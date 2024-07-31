Step-by-step: https://learning.sap.com/learning-journeys/implementing-sap-s-4-hana-cloud-public-edition/deploying-content-in-the-sap-s-4hana-cloud-starter-system
### Create project per SAP S/4HANA Cloud Started System tenant 

+ The project is created in the Central Business Configuration 
+ In order to access the SAP Central Business Configuration, the Super User must grant access to the user in the SAP Cockpit and validate the access in the [[SAP Profile Management]].

#### 1) Add team members in projects 
+ Even though the access were granted in the Cockpit, the user must be added in [[SAP Cloud Identify Services]] before, otherwise they won't show up. ==Also, to validate the user added, the admin must run the job to "User Sync" in [[Identity Provisioning]].== 

#### 2) Define Scope
+ Firstly we must to define a region and language. Then it will automatically show the "bundles", which are a grouping of Cloud Services and Systems, tailored to individual business need. When added the bundle in the project, it creates the touch point in SAP for Me. 
![[SAP - Project Bundle]]

*** In order to automatically create the process, we must add "Include Demo Data"
### 3) Request a Quality system
+ If it's not update it will ask to update. 

![[Pasted image 20240718180521.png]]