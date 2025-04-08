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

### SAP CI (BTP - IS)

Cloud Integration is a set of services and tools provided by SAP on its cloud-base BTP. 

**How CI integrates with Datasphere?**
1. CI can load the data directly in Datasphere using JDBC protocol.
2. CI can consume the exposed OData V4 service from Datasphere.
3. CI can make use of the open connector on BTP IS if the open connector connection is activated in Datasphere.

Relevant Links: 
https://help.sap.com/docs/SAP_DATASPHERE/be5967d099974c69b77f4549425ca4c0/5d55da5514b240ff8d3a970bf7dc6705.html
https://community.sap.com/t5/technology-blogs-by-sap/sap-datasphere-sap-hana-cloud-hdi-ci-cd-automation-approach/ba-p/13533807
https://community.sap.com/t5/technology-blogs-by-sap/sap-datasphere-sap-hana-cloud-hdi-automation-ci-cd-pipelines-details/ba-p/13539235

