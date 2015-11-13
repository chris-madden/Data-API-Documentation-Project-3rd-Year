##Project Title

######Data Representation and Querying Project 2015

##Name

######Christy Madden

###Introduction

This project is using the dataset 'Galway City Parking Locations' which can be found at the following url https://data.gov.ie/dataset/galway-city-car-parking-locations. The design and documentation for the dataset is below.

###About the api

This is an api designed for developers who may need data based on car parking locations in Galway. It is accessed through http. The basic url structure is below:

     www.galway.ie/carpark_api/?

###About the dataset

The dataset is originally in the CSV (comma separated values) format and is formatted into json when requested. The dataset can be found in this repository.

The dataset has 17 rows and covers all public car parks in the city. This dataset will continue to grow as it is expanded to to cover the surrounding areas of Galway City. 

The dataset contains 12 fields which includes different grid systems for locating the car parks.

Rows are determined by the objectid

######Contents in dataset

|Field|Value|
|---|---|
| X | The long version of the latitude coordinates|
|Y| The long version of the longitude coordinates|
| Objectid |The id number of the row|
|Name|The name of the carpark|
| Type |The type of carpark|
|No_Spaces|The number of spaces in the carpark|
| Lat |The short version of the latitude coordinates|
|Long|The short version of the longitude coordinates|
| Eastitm |The east ITM coordinates|
|Northitm|The north ITM coordinates|
| Eastig |The east IG coordinates|
|Northig|The north IG coordinates|

*For those who need more inforamtion about the different coordinate systems check out the links below*

* [Lat & Long](https://www.learner.org/jnorth/tm/LongitudeIntro.html)
* [ITM](https://en.wikipedia.org/wiki/Irish_Transverse_Mercator)
* [IG](https://en.wikipedia.org/wiki/Irish_grid_reference_system)

---

####/Retrieve

######URL Structure 

    www.galway.ie/carpark_api/retrieve?field=[field]&limit[limit]

######Method

GET 

######Arguments 

|Argument|Description|
|---|---|
| field | The name of the fields you want. (Use ‘all’ to retrieve all fields for the row) **E.G field=all**|
|limit| The number of rows you want returned (defaults to 20) **E.G limit=5**|

######Returns

An array of JSON objects with carpark information

######Sample Response

```javascript
[ {"type": "Multistorey Carpark", "no_spaces": 88}, {"type": "Pay/Surface Carpark", "no_spaces": 100}]
```

---

####/Add

######URL Structure 

     www.galway.ie/carpark_api/add?
    
######Method

POST

######Arguments

|Argument|Description|
|---|---|
| X |  The long version of the latitute coordinates|
|Y| The long version of the longtitute coordinates|
| Objectid | The id number of the row|
|Name| The name of the carpark|
| Type | The type of carpark|
|No_Spaces| The number of spces in the carpark|
| Lat | The latitude of the carpark|
|Long|The longtitutde of the carpar|
| Eastitm |The east ITM coordinates|
|Northitm|The north ITM coordinates|
| Eastig |The east IG coordinates|
|Northig|The north IG coordinates|

*These fields must be sent in the body of the request*

######Returns

Returns a JSON object with a success value stating whether your post worked or not and shows the values paired with the fields you wanted

######Sample Response

```javascript
{    "success": true,
     "X": "1.87654", 
     "Y": "2.45986", 
     "objectid" : 20, 
     "name": "shop street carpark", 
     "type": "multistorey carpark",
     "No_spaces": 100,
     "Lat": 1.877,
     "Long": 2.60,
     "Eastitm": 1498.987
     "Northitm": 2193.564
     "Eastig": 298764.18,
     "Northig": 3981.87
 }
```

---

####/Update

######URL Structure 

     www.galway.ie/carpark_api/update?objectid=[id number]&field=[field]&values=[value]
    
######Method

PUT

######Arguments

|Argument|Description|
|---|---|
| objectid  | The number of the row you want to change|
|field | The name of the fields you want to change|
|value  |The values for the new field|

*Multiple fields for the row can be changed in one go. Add a comma between fields and make sure you have the correct values for them also separated by a comma*

######Returns

Returns a JSON object with a success value stating whether your update worked or not and shows the new values paired with the fields you wanted.

######Sample Response

```javascript
{    "success": true, 
     "objectid" : 7, 
     "name": “city center carpark”, 
     "type": “Surface Carpark (free parking)”
 }
```

---

####/Delete

######URL Structure

      www.galway.ie/carpark_api/delete?objectid=[id number]
     
######Method

DELETE 

######Arguments

|Argument|Description|
|---|---|
|objectid| The number of the row you want to delete|

*Only full rows can be deleted, when you choose the row using the objectid all in information connected to this row will be deleted*

######Returns

A JSON object with a delete value saying whether or not it worked and the number of the row that was deleted

######Sample Response

```javascript
{   "Deleted": true, 
    "objectid" : 9}
```







