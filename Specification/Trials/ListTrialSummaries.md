## Get List of Trial Summaries [/brapi/v1/trials]

Scope: PHENOTYPING.
Status: ACCEPTED.
Implementation target date: PAG2016.

###### Response data types

| Variable                | Datatype        | Description                                             | Required |
| ----------------------- | --------------- | ------------------------------------------------------- | :------: |
| trialDbId               | string          | string database identifier, not necessarily a Primary Key |    Y     |
| trialName               | string          | Human readable name                                     |    Y     |
| programDbId             | string          | string database identifier, not necessarily a Primary Key |          |
| programName             | string          |                                                         |          |
| startDate               | Date (ISO 8601)          |                                                         |          |
| endDate                 | Date (ISO 8601)          |                                                         |          |
| active                  | boolean         |                                                         |          |
| studies                 | array of object | List of studies                                         |          |
| studies.studyDbId       | string          | Study database identifier                               |          |
| studies.studyName       | string          | Study  name                                             |          |
| studies.locationName    | string          | Study location name                                     |          |
| additionalInfo          | object          | Additional arbitrary info on the trial                  |          |

### List of trial summaries [GET /brapi/v1/trials{?programDbId}{?locationDbId}{?pageSize}{?page}{?active}{?sortBy}{?sortOrder}]

+ Parameters
    + programDbId (optional, string, `1`) ... Program filter to only return trials associated with given program id.
    + locationDbId (optional, string, `212`) ... Filter by location
    + pageSize (optional, integer, `1000`) ... The size of the pages to be returned. Default is `1000`.
    + page (optional, integer, `0`) ... Which result page is requested. The page indexing starts at 0 (the first page is 'page'= 0). Default is `0`.
    + active (optional, boolean, `true`) ... Filter active status true/false. 
    + sortBy (optional, string, `studyDbId`) ... Sort order. Name of the field to sorty by.
    + sortOrder (optional, string, `asc`) ... Sort order direction: asc/desc
    
+ Response 200 (application/json)

        {
            "metadata": {
                "pagination": {
                    "pageSize": 1000,
                    "currentPage": 0,
                    "totalCount": 2,
                    "totalPages": 1
                },
                "status" : [],
                "datafiles": []
            },
            "result": {
                "data": [ 
                    {
                        "trialDbId" : "1",
                        "trialName" : "InternationalTrialA",
                        "programDbId": "27",
                        "programName": "International Yield Trial",
                        "startDate": "2007-06-01",
                        "endDate"  : "2008-12-31",
                        "active" : "false", 
                        "studies" : [
                            {
                                "studyDbId" : "1",
                                "studyName" : "Zimbabwe Yield Trial",
                                "locationName" : "Zimbabwe"
                            },
                            {
                                "studyDbId" : "2",
                                "studyName" : "Kenya Yield Trial",
                                "locationName" : "Kenya"
                            }
                        ],
                        "additionalInfo" : {
                            "property1Name" : "property1Value",
                            "property2Name" : "property2Value",
                            "property3Name" : "property3Value"
                        }
                    },
                    {
                        "trialDbId" : "2",
                        "trialName" : "InternationalTrialB",
                        "programDbId": "35",
                        "programName": "International Yield Trial 2: Return of the Trial",
                        "startDate": "2008-06-01",
                        "endDate"  : "2009-12-31",
                        "active" : "true", 
                        "studies" : [
                            {
                                "studyDbId" : "3",
                                "studyName" : "Zimbabwe Yield Trial",
                                "locationName" : "Zimbabwe"
                            },
                            {
                                "studyDbId" : "4",
                                "studyName" : "Kenya Yield Trial",
                                "locationName" : "Kenya"
                            }
                        ],
                        "additionalInfo" : {
                            "property1Name" : "property1Value",
                            "property2Name" : "property2Value",
                            "property3Name" : "property3Value"
                        }
                    }
                ]
            }
        }        

