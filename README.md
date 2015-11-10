#Project Title

######Data Representation and Querying Project 2015

#Name

######Christy Madden

#Introduction

This project is using the dataset 'Galway City Parking Locations' which can be found at the following url https://data.gov.ie/dataset/galway-city-car-parking-locations. The design and documentation for the dataset is below.

#About the dataset

The dataset is originally in the CSV (comma separated values) format and is formatted into json. The dataset can be found and downloaded from https://data.gov.ie/dataset/galway-city-car-parking-locations/resource/d967950d-faab-45ad-815d-211c9bcfb38e.

The dataset has 17 rows and covers all public car parks in the city. This dataset will continue to grow as it is expanded to to cover the surrounding areas of Galway City. 

The dataset contains 12 fields which includes different grid systems for locating the car parks.
The first 2 fields are an older coordinates system and may not be of use to you, we recommend you ignore these and choose one of the more up to date coordinate systems

*Out of date fields*

|  X |  Y |
|---|---|

*Recommended fields to use*

|OBJECTID|NAME|TYPE|NO_SPACES|LAT|LONG|EastITM|NorthITM|EastIG|NorthIG|   
|---|---|---|---|---|---|---|---|---|---|

**Note on what type of information will be retrieved with each field**

1. X: -9.053499750875776
2. Y: 53.273082469830108
3. OBJECTID: 1
4. NAME: Market St
5. TYPE: Pay/Surface Carpark, Multistorey Carpark, Surface Carpark (free parking)
6. NO_SPACES: 88
7. LAT: 53.273
8. LONG: -9.054
9. EastITM: 529691.955
10. NorthITM: 725294.803
11. EastIG: 129726.012
12. NorthIG: 225265.639

*For those who need more inforamtion about the different coordinate systems check out the links below*

[Lat & Long](https://www.learner.org/jnorth/tm/LongitudeIntro.html)

[ITM](https://en.wikipedia.org/wiki/Irish_Transverse_Mercator)

[IG](https://en.wikipedia.org/wiki/Irish_grid_reference_system)

####Retrieve Data

**URL Structure** 

*www.galwaycity.ie/carpark_api/?field=[ Name of field ]&limit[ Number of rows ]*

**Method** 

GET 

Arguments 

|Argument|Description|
|---|---|
| field |  *The name of the fields you want. (Use ‘all’ to retrieve all fields for the row)* **E.G field=all**|
|limit| *The number of rows you want returned (defaults to 20)* **E.G limit=5**|











