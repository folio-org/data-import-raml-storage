## Checklist to go through when updating a schema

Go through the following steps in case of a schema update for any entity
 
1. Update dependency on raml-storage in each of the following modules:
    * [mod-source-record-storage](https://github.com/folio-org/mod-source-record-storage)
    * [mod-data-import-converter-storage](https://github.com/folio-org/mod-data-import-converter-storage)
    * [mod-source-record-manager](https://github.com/folio-org/mod-source-record-manager)
    * [mod-data-import](https://github.com/folio-org/mod-data-import)

2. Update dependency on raml-storage in [data-import-processing-core](https://github.com/folio-org/data-import-processing-core). 
Since it is a library, the changes in the modules that use it will be applied only after the dependency update - set current development version of data-import-processing-core for the modules below:
    * [mod-inventory](https://github.com/folio-org/mod-inventory) 
    * [mod-source-record-manager](https://github.com/folio-org/mod-source-record-manager)
    * [mod-source-record-storage](https://github.com/folio-org/mod-source-record-storage)
   
    If correct SNAPSHOT version of data-import-processing-core is already set, make sure to rebuild the main branch of the module, otherwise changes won't be picked up
  
3. Check whether updates affect the API in any of the modules - review [Interface change checklist](https://dev.folio.org/guidelines/pull-requests-checklists/). If so - consider bumping the API version for that module.

4. Check whether applied changes concern the following users. 
    * [mod-quick-marc](https://github.com/folio-org/mod-quick-marc)
    * [mod-marccat](https://github.com/folio-org/mod-marccat) 
    
    Notify teams managing those modules and create JIRA ticket for them to update their dependencies if needed.
