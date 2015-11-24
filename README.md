# BuildCypher.js

Generate `LOAD CSV` Cypher script given configuration data of the format:

~~~
{
    "nodes": [
        {
            "filename": "legislators.csv",
            "labels": ["Legislator"],
            "properties": [
                {
                    "headerKey": "thomasID",
                    "neoKey": "thomasID",
                    "dataType": "int",
                    "index": true,
                    "primaryKey": true,
                    "foreignKey": false,
                    "skip": false
                },
                {
                    "headerKey": "firstName",
                    "neoKey": "firstName",
                    "dataType": "string",
                    "index": false,
                    "primaryKey": false,
                    "foreignKey": false,
                    "skip": false
                },
                {
                    "headerKey": "lastName",
                    "neoKey": "lastName",
                    "dataType": "string",
                    "index": false,
                    "primaryKey": false,
                    "foreignKey": false,
                    "skip": false
                },
                {
                    "headerKey": "type",
                    "neoKey": "body",
                    "dataType": "string",
                    "index": false,
                    "primaryKey": false,
                    "foreignKey": false,
                    "skip": false
                },
                {
                    "headerKey": "party",
                    "neoKey": "party",
                    "dataType": "string",
                    "primaryKey": false,
                    "foreignKey": false,
                    "skip": false
                }
            ]
        },
        {
            "filename": "committees.csv",
            "labels": ["Committee"],
            "properties": [
                {
                    "headerKey": "thomasID",
                    "neoKey": "thomasID",
                    "dataType": "string",
                    "index": true,
                    "primaryKey": true,
                    "foreignKey": false,
                    "skip": false
                },
                {
                    "headerKey": "jurisdiction",
                    "neoKey": "jurisdiction",
                    "dataType": "string",
                    "index": false,
                    "primaryKey": false,
                    "foreignKey": false,
                    "skip": false
                },
                {
                    "headerKey": "name",
                    "neoKey": "name",
                    "dataType": "string",
                    "index": false,
                    "primaryKey": false,
                    "foreignKey": false,
                    "skip": false
                },
                {
                    "headerKey": "type",
                    "neoKey": "body",
                    "dataType": "string",
                    "index": false,
                    "primaryKey": false,
                    "foreignKey": false,
                    "skip": false
                },
                {
                    "headerKey": "url",
                    "neoKey": "url",
                    "dataType": "string",
                    "index": false,
                    "primaryKey": false,
                    "foreignKey": false,
                    "skip": false
                }
            ]
        }
    ],
    "relationships": [
        {
            "filename": "committee-members.csv",
            "from": {
                "filename": "legislators.csv",
                "neoKey": "thomasID",
                "fileKey": "legislatorID",
                "label": "Legislator"
            },
            "to": {
                "filename": "committees.csv",
                "neoKey": "thomasID",
                "fileKey": "committeeID",
                "label": "Committee"
            },
            "name": "SERVES_ON"
        }
    ]

}
~~~