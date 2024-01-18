# Documentation


Opisi mikrostoritev sta na voljo na
- https://github.com/RSO-project-finances/expences/
- https://github.com/RSO-project-finances/statistics/,  

oboje v Pripadajočih README.md datotekah.  
Nekatere uporabne povezave:
- http://20.228.195.151/v1/expenses/
- http://20.228.195.151/v1/expenses/2
- http://20.228.195.151/v1/statistics
- http://20.228.195.151/openapi
- http://20.228.195.151/api-specs/ui/?url=http://http://20.228.195.151/openapi&oauth2RedirectUrl=http://localhost:8080/api-specs/ui/oauth2-redirect.html
- http://20.228.195.151/health/live
- http://20.228.195.151/health/ready

Primeri poizvedb:  

### REST

POST http://20.228.195.151/v1/expenses/  
Content-Type: application/json

{  
  "kind": "food",  
  "date_occurrence": "2018-07-14T14:31:30",  
  "price": 3.7,  
  "description": ""  
}  

POST http://20.228.195.151/v1/expenses/
Content-Type: application/json
  

{
"kind": "sdfsdf",  
"date_occurrence": "2018-07-14T14:31:30",  
"price": 4.5,  
"description": ""  
}  

PUT http://4.156.168.114/v1/expenses/2  
Content-Type: application/json  

{
  "kind": "food",  
  "date_occurrence": "2012-07-04T15:36:38Z",  
  "price": 3.7,  
  "description": ""  
}  

GET http://20.228.195.151/v1/expenses/2  

GET http://20.228.195.151/v1/statistics  

DELETE http://20.228.195.151/v1/expenses/2  

### GraphQL

query MyQuery {  
  allExpenses(pagination: {offset: 0, limit: 10},
    						sort: {fields: [{field: "kind", order: ASC}]}) {  
    result {  
    	expenseId  
    	description  
      dateOccurrence  
    }  
    pagination {  
      offset  
      limit  
      total  
    }  
 }  
}  

query MyQuery {  
  expenses(id: 1) {  
    dateOccurrence  
    description  
    expenseId  
    kind  
  }  
}  

mutation addImageMetadata {  
  addExpense(expense: {dateOccurrence: "2023-11-27T16:36:38Z", description: "Uploaded via GraphQL"}){  
    expenseId  
    kind  
    description  
  }  
}