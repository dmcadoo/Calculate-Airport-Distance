# Calculate-Airport-Distance
Calculate Airport distances from Airport itineraries.

# Instructions
Track the point-to-point mileage between their top destinations and compare it to the mileage given by the carriers in .csv file.
Is there any errors in the data?

# Process
First,Load data and dependencies.
Review data, look for  missing or incomplete data. A visual inspection  of df.describe() & df.info() No missing data is apparent.
Creating a new dataframe and sorting on 'Departure Code'  sorts our "departure Code" column   ascending to show any discrepancies in any corresponding Lat/Lon s.
!!!!
Just taking a sample and looking at the top 50 rows, we see that there is mismatching data in the "Departure Lat" & "Departure Lon" columns for the same Airport code. 
And
While doing a similar sort on "Arrival Code" we see that similar Lat/Lon s do not match "Departure Lat/Lon"s.
At this point, I would be skeptical of the entire data set of Lat/Lon Departing and Arriving. The data would need to be corrected in the internal database, and resampled. 

If the data for Lat/Lon was correct we would then have to calculate distances from airport to airport using a great circle distance trigonometric function. I was unaware of how to do this so I googled for the equation.
Searching stackoverflow for a python version of the equation, I found one that could iterate through the database.
running calculation and adding new column "distance" to every row. 
