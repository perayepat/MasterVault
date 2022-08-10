Student Json

``` Json
	
{
    "studentID" : 555030,
    "studentNumber" : 35678920,
    "firstName": "Rack",
    "lastName": "Jackon",
    "gender": "man",
    "dateOfBirth": 19940520,
    "email" : "RackJackon@gmail.com",
    "clubs": [{ 
        
        "clubID" : 1 ,
        "clubName" : "Cycling",
          "Staff" : [{
                  "name" : "Rael Lissons",
                  "Email" : "RaelLissons@gmail.com",
                  "role" : ["clubHead", "lecturer"]
              }],
        "clubDescription" : "Teaching students how to cycle",
        "numOfMembers" : 25
        
    }],
    "qualification": [
    {
      "qualificationID": 800,
      "typeOfQualification": "Degree", 
      "description": "Business Communications",
       "Staff" : [{
                  "name" : "Deirde Constance",
                  "Email" : "Deirdeconstance@gmail.com",
                  "role" : "Coordinator"
              }],
      "modules" : [{
              "moduleID": 250,
              "name": "Accounting",
              "description": "this is and that",
              "numTests": 5,
              "nextDueDate" : "15 Aug 2022",
              "Staff" : [{
                  "name" : "Demi Swart",
                  "Email" : "DemiSwart@gmail.com",
                  "role" : "lecturer"
              }]
            },
            {
              "moduleID": 450,
              "name": "Business",
              "description": "this is and that",
              "numTests": 4,
              "nextDueDate" : "20 Aug 2022"
              
           
            }]}
  ],
    "phoneNumbers": [
        { "type": "home", "number": "7383627627" },
        { "type": "emergency", "number": "7383627627" }
    ]
 
}
```
