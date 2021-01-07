# Food Scarcity in New York City

Food scarcity is a well-known problem in New York City. It refers to the fact that some areas lack healthy food options that are usually provided by supermarkets or fresh food stores. These "food deserts", which they are colloquially called, often lead to higher rates of obesity and obesity related illnesses. 

The goal of this project was to use data collected from Foursquare to find areas that had similarities in terms of the amount of healthy food options they offered. 

### Data
The first source of data was from the various Wikipedia pages that held New York City's data. New York is unique in that while it is a single city, each borough is it's own county. This is the reason behind each borough having it's own webpage and webscraping code. 

The second source was from the FourSquare API that provided us the different venues in each of the locales. The combination of the two would eventually be what we use to cluster the neighborhoods. 

### Methodology
1. Using the Wikipedia pages, we webscrape the name of each neighborhood in each of the five boroughs. 
2. Using Geopy, we give each neighborhood a Latitiude and Longitude value. 
3. Next comes the use of the Foursquare API, we use it to find the venues and their categories within a radius of the coordinates. 
4. Remove all venues that were not part of the group that we decided were necessary for the clustering. Venues that were deemed relevant for this project are in categories including:
    * Fast Food Restaurants
    * Supermarkets
    * Markets
    * Grocery Store
5. All venue entries that were not categorized as the above were removed from the dataframe. From there an average was found for each neighborhood. This means that the percentage of fast food stores in the total for food places was found. This applies to all of the options listed above. 
6. Principal Component Analysis was done next in order to determine the amount of variance each of the features explained. The results were used in KMeans clustering. 
7. Looping though the possible number of clusters, the number was narrowed down by looking at the Silhouette Score and the Elbow Curve.
8. Mapping the results included using Folium. 



### Results
