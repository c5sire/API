### Germplasm search through POST [POST /brapi/v1/germplasm-search]

Use POST for large queries (>2K bytes).

+ Request (application/json)

        {
            "germplasmPUIs" : [ "http://www.crop-diversity.org/mgis/accession/01BEL084609", "doi:10.15454/328757862534E12" ],
            "germplasmDbIds" : [ "986", "01BEL084609" ],
            "germplasmSpecies" : [ "aestivum", "vinifera" ],
            "germplasmGenus" : [ "Solanum", "Triticum" ],
            "germplasmNames" : [ "XYZ1", "Pahang" ],
            "accessionNumbers": [ "ITC0609", "ITC0685" ],
            "pageSize" : 100,
            "page": 1
        }

+ Response 200 (application/json)

        {
            "metadata": {
                "status": [],
                "datafiles": [],
                "pagination": {
                    "pageSize": 100,
                    "currentPage": 1,
                    "totalCount": 102,
                    "totalPages": 2
                }
            },
            "result": {
                "data": [
                    {
                        "germplasmDbId": "01BEL084609",
                        "defaultDisplayName": "Pahang",
                        "accessionNumber": "ITC0609",
                        "germplasmName": "Pahang",
                        "germplasmPUI": "http://www.crop-diversity.org/mgis/accession/01BEL084609",
                        "pedigree": "TOBA97/SW90.1057",
                        "germplasmSeedSource": "Female GID:4/Male GID:4",
                        "synonyms": [ ],
                        "commonCropName": "banana",
                        "instituteCode": "01BEL084",
                        "instituteName": "ITC",
                        "biologicalStatusOfAccessionCode": 412,
                        "countryOfOriginCode": "UNK",
                        "typeOfGermplasmStorageCode": [10],
                        "genus": "Musa",
                        "species": "acuminata",
                        "taxonIds": [
                          {
                            "sourceName":"ncbiTaxon",
                            "taxonId":"http://purl.obolibrary.org/obo/NCBITaxon_4641"
                          }, {
                            "sourceName":"ciradTaxon",
                            "taxonId":"23-E"}],
                        "speciesAuthority": "",
                        "subtaxa": "sp malaccensis var pahang",
                        "subtaxaAuthority": "",
                        "donors": [
                            {
                                "donorAccessionNumber": "",
                                "donorInstituteCode": "",
                                "germplasmPUI": ""
                            }
                        ],
                        "acquisitionDate": "1947-01-31"
                    }, {
                        "germplasmDbId": "03REL084609",
                        "defaultDisplayName": "Pah",
                        "accessionNumber": "ITC0685",
                        "germplasmName": "Pah",
                        "germplasmPUI": "doi:10.15454/328757862534E12",
                        "pedigree": "TOBA97/SW90.1057",
                        "germplasmSeedSource": "Female GID:4/Male GID:4",
                        "synonyms": [ ],
                        "commonCropName": "banana",
                        "instituteCode": "01BEL084",
                        "instituteName": "ITC",
                        "biologicalStatusOfAccessionCode": 412,
                        "countryOfOriginCode": "UNK",
                        "typeOfGermplasmStorageCode": [10],
                        "genus": "Musa",
                        "species": "acuminata",
                        "taxonIds": [
                          {
                            "sourceName":"ncbiTaxon",
                            "taxonId":"http://purl.obolibrary.org/obo/NCBITaxon_4641"
                          }, {
                            "sourceName":"ciradTaxon",
                            "taxonId":"23-E"}],
                        "speciesAuthority": "",
                        "subtaxa": "sp malaccensis var pah",
                        "subtaxaAuthority": "",
                        "donors": [
                            {
                                "donorAccessionNumber": "",
                                "donorInstituteCode": "",
                                "germplasmPUI": ""
                            }
                        ],
                        "acquisitionDate": "1977-01-31"
                    }
                ]
            }
        }

