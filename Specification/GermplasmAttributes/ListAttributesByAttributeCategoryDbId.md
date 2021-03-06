## List attributes available [/brapi/v1/attributes]
Scope: OTHER. Status: ACCEPTED.
Implementation target date: PAG2016

### Attributes by attributeCategoryDbId [GET /brapi/v1/attributes{?attributeCategoryDbId}{?pageSize}{?page}] 

List available attributes.

###### Response data types
|Variable|Datatype|Description|Required|  
|------|------|------|:-----:|
|attributeCategoryDbId|string|internal database identifier, not stable |Y|
|code|string|abbreviation||
|uri|string|reference to external documentation, ontology etc.||
|name|string|for display, and stable identifier unique in the database|Y|
|description|string|||
|datatype|string|e.g. Categorical, Numeric, Boolean||
|values|array of string|array of all possible values for this attribute|Y|
+ Parameters
   + attributeCategoryDbId (optional, string, `2`) ... filter for kind of attributes
   + pageSize (optional, integer, `1000`) ... The size of the pages to be returned. Default is `1000`.
   + page (optional, integer, `0`) ... Which result page is requested. The page indexing starts at 0 (the first page is 'page'= 0). Default is `0`.

+ Response 200 (application/json)

        {
            "metadata" : {
                "pagination": {
                    "pageSize": 1000,
                    "currentPage": 0,
                    "totalCount": 1,
                    "totalPages": 1
                },
                "status": [],
                "datafiles": []
            },
            "result" : {
                "data" : [
                    {
                        "attributeCategoryDbId": "1",
                        "code": "RHT",
                        "uri": "http://www.cropontology.org/rdf/CO_321:0000020",
                        "name": "Rht-B1b",
                        "description": "Allele of marker 11_4769, diagnostic for allele b of reduced-height gene Rht-B1",
                        "datatype": "Categorical",
                        "values": ["Present", "Absent", "Heterozygous"]
                    }
                ]
            }
        }
