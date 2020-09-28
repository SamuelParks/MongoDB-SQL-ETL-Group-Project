# True-Safe-Cars

The objective of this ETL project was to provide our client, TrueSafeCars.com, with a database containing a consolidated inventory their cars.  Our client was formed by buying inventory from two major used car dealership chains.  To support their business goals, we were tasked with this ETL project with the following goals:
1.	Consolidate the inventory into a central database 
2.	Assign the inventory to one of TrueSafeCars.com’s five main offices 
3.	Identify which vehicles should be sold at auction (vs. selling to the public) 
4.	Identify which vehicles meet our safety guidelines 
5.	Identify recall information per vehicle 

### Extract Requirements 
Pull vehicle inventory data from the two dealerships we purchased: 
*	Data for purchased dealership #1: Kaggle.com (https://www.kaggle.com/jpayne/852k-used-car-listings)
*	Data for purchased dealership #2: Kaggle.com (https://www.kaggle.com/austinreese/craigslist-carstrucks-data) 

### Transform Requirements 
Once all of the vehicle inventory data has been extracted, perform the following transformations: 
*	Remove duplicate VIN numbers
*	Assign the inventory to one of five main office locations. The client has provided a CSV file with the State-to-Main Office mapping. Our 5 main office locations are: 
    *	Northeast Main Office 
    *	Southeast Main Office 
    * Midwest Main Office 
    * Southwest Main Office 
    * West Main Office 
*	Assign each vehicle an overall safety rating using an API from NHTSA.gov (https://webapi.nhtsa.gov/Default.aspx?SafetyRatings/API/5)
*	Determine the number of open recalls per vehicle using an API from NHTSA.gov  (https://webapi.nhtsa.gov/Default.aspx?Recalls/API/83)

The vehicle inventory should have a column to indicate if the vehicle is ready to be sold to the public or not: 
*	Vehicles 20 years old or older should be sold at auction 
*	Vehicles with an overall poor safety rating should be sold at auction 
*	Vehicles in poor condition (if this information is available in the inventory data) should be sold at auction 

### Load Requirements 
Load transformed data into a central database (NoSQL). The central database should have tables that can be easily queried to retrieve: 
*	Vehicles assigned to each main office 
*	Vehicles that are ready to be sold to the public 
*	Vehicles that should be sold at auction 
*	Overall safety rating for each vehicle 
*	Recalls that apply to each vehicle 

Screenshot of MongoDB Compass:
![image](https://user-images.githubusercontent.com/61704055/94388308-a42b2300-011a-11eb-90ce-742e8563f8f5.png)



GT-DS-BC-Proj-1
