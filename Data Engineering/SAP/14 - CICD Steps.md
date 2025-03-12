Continuous Integration & Delivery
### Tutorial
https://community.sap.com/t5/technology-blogs-by-sap/sap-datasphere-sap-hana-cloud-hdi-ci-cd-automation-approach/ba-p/13533807

## Steps for configuration

https://help.sap.com/docs/continuous-integration-and-delivery/sap-continuous-integration-and-delivery/optional-enabling-api-usage


### HDI Container 
https://help.sap.com/docs/HANA_SERVICE_CF/cc53ad464a57404b8d453bbadbc81ceb/93cdbb1bd50d49fe872e7b648a4d9677.html

Services plan explanations: 
https://help.sap.com/docs/hana-cloud-database/sap-hana-cloud-sap-hana-database-developer-guide-for-cloud-foundry-multitarget-applications-sap-business-app-studio/sap-hana-cloud-deployment-infrastructure-services#the-%E2%80%9Chdi-shared%E2%80%9D-service-plan

How to get the GUID from SAP HANA Cloud

https://help.sap.com/docs/sap-hana-service-for-sap-btp-in-sap-and-microsoft-azure-regions/sap-hana-service-for-sap-btp-in-azure-regions-validation/finding-guid-of-tenant-database-service-instance

Bind the HDI Container: 

https://community.sap.com/t5/technology-blogs-by-sap/sap-datasphere-enable-sap-hana-development-infrastructure-hdi/ba-p/13602509

### Command Line Interface 

* Node.js based command-line interface.
* Interact with a tenant from a terminal or command line.
* Authenticate the business User while logging into CLI 

https://help.sap.com/docs/SAP_DATASPHERE/d0ecd6f297ac40249072a44df0549c1a/f7d5eddf20a34a1aa48d8e2c68a44e28.html

CLI - SAP: https://help.sap.com/docs/SAP_DATASPHERE/d0ecd6f297ac40249072a44df0549c1a/7e9203d091b44d7f88a8c274498c1b64.html

Solve Error Authentication Login: https://userapps.support.sap.com/sap/support/knowledge/en/3461484

Troubleshoots: https://community.sap.com/t5/technology-blogs-by-sap/faq-amp-troubleshooting-guide-for-sap-datasphere-cli/ba-p/13550029

### Tutorials SAP CICD

- Get Started with an SAP Fiori Project in SAP Continuous Integration and Delivery: https://developers.sap.com/tutorials/cicd-start-fiori.html
	- It needs a Fiori app connected to a Git repository, so I followed this tutorial before: https://developers.sap.com/tutorials/fiori-tools-generate-project.html

Possible errors: 

- If the error is related to the "mta.yaml" file, it's because the CICD is not able to find it in the folder. It must be in the main path. 
E.g.: 

![[Pasted image 20250312094146.png]]

Also, there is a possibility that the SAP Fiori app is not generating the file. So, during the SAP Fiori app creation process it's important to this field be activated: 
![[Pasted image 20250312094928.png]]

- Error related to Cloud Foundry acceptance: 
  ![[Pasted image 20250312095103.png]]

Correct by validating the CF information. 