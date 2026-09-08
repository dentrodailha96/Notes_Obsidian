 
## Development Tenant
 
 Build own custom development based on lifecycle-stable SAP Objects (Developer Extensibility). The Developer Extensibility includes: ABAP RESTful Application Programming model (RAP), Eclipse based IDE with debugger, troubleshooting and testing tool support and ABAP software lifecycle support.
  https://help.sap.com/docs/SAP_S4HANA_CLOUD/6aa39f1ac05441e5a23f484f31e477e7/e3527dfa1c5a41f69d4e63691f174f0a.html
 
Once you have finalized your development and configuration projects in Development System, you can transport them only to Test System and then to the Production System.

## Customizing Tenant

This tenant allows you to configure your ==activities based on the reference content from SAP Central Business Configuration== and to create low-code custom developments in Key User applications, this is called Key User Extensibility. 
The Key User Extensibility is based on applications and features that help you customize applications and their UIs, reports, email templates, and form templates. Using extensibility apps, you can create custom fields, data source extensions, and implementation descriptions for specific business contexts to enhance predelivery applications that are extensible in order to adapt them to your business needs. You can also create custom CDS views based on predelivered data sources. You can create custom business objects with UIs. You can also add custom logic to custom business objects. You can thus create your own applications based on custom business objects. You can use Custom Analytical Queries to create new queries or reuse predefined queries. You use fields from CDS views to create a query.
https://community.sap.com/t5/enterprise-resource-planning-blogs-by-sap/extensibility-in-the-development-system-of-a-3-system-landscape/ba-p/13570453


***  it's not possible to transport items between Development and Customizing Tenant.

![[Pasted image 20240802130924.png]]