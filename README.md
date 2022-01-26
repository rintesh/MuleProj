# muleproj
 
Branch: DEV

Logic:
    Contact and Leads creation in database
        Contacts:
            Should contain all the columns
        Leads:
            Should contain csid and emailAddress



25-01-2022: **CHANGELOGS**
            Added Batch Job in Implementation Flow
            Summary:
                Batch job allowed to have n number of errors (Max error: -1)
                3 Batch Steps used
                Contacts:
                    Used for handling contact records ( #[ !( isEmpty(payload.id) ) and !( isEmpty(payload.emailAdd) )  ] )
                Leads:
                    Used for handling leads records ( #[!( isEmpty(payload.id) ) and !( isEmpty(payload.emailAdd) ) and ( isEmpty(payload.gender) ) and ( isEmpty(payload.firstName) ) and ( isEmpty(payload.lastName) ) and ( isEmpty(payload.DOB ))] )
                Error_step:
                    Used for handling the errors generated in Contacts or Leads batch step

26-01-2022: **CHANGELOGS**
            Added configurations
                - DEV.yaml
                - SIT.yaml
                - STAGING.yaml
                - PROD.yaml
            Added blowfish encryption
            Added Bulk insert for Contact and Leads and mapped the data to the database table columns.