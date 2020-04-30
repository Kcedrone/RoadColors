# RoadColors

United States:
Plot roads in a US city, coloring each by its designation (e.g. Street, Road, Avenue)

Here are the steps I took to make a map of Boston-area roads from [erdavis1's wonderful RoadColors code](https://github.com/erdavis1/RoadColors)

1. [Download and install R](https://cran.r-project.org/doc/FAQ/R-FAQ.html#How-can-R-be-installed_003f)

1. Run R and install the required packages
    1. `install.packages("sf")`
    1. `install.packages("foregin")`
    1. `install.packages("tidyverse")`
    1. `install.packages("lwgeom")`
    
1. Clone the [RoadColors repo](https://github.com/erdavis1/RoadColors).

1. Rename `UnitedStates` to `UnitedStates.r`

1. Within the RoadColors repo local directory:
    * Make folder called “FeatNames”
    * Make folder called “Roads”
    * Make folder called “IndivRoads” (this will be the output directory)

1. Identify the latitude and longitude for the center of the map
    * The lat and long are in the [URL of Open Street Maps](https://www.openstreetmap.org/search?query=boston%2C%20ma#map=12/42.3667/-71.0591).
        * latitude = 42.3667, longitude = -71.059
    * Put the latitude and longitude in `Line 9` of `UnitedStates.r`
    
1. Put the city name on `Line 10` of `UnitedStates.r`
    
1. Identify the names of counties within 15 miles of this point.
    *  I did a [DuckDuckGo images search for "Massachusetts county map"](https://duckduckgo.com/?q=massachusetts+county+map&t=hy&ia=images&iax=images).
        * Suffolk
        * Middlesex
        * Norfolk
        
1. Identify the GEOIDs of the counties. 
    * This site is very helpful: [https://census.missouri.edu/geocodes/](https://census.missouri.edu/geocodes/). 
        * 25025
        * 25017
        * 25021

1. Put the GEOIDs in `Line 11` of `UnitedStates.r`

1. Download and unzip the roads shapefiles for each GEOID: 
    * [ftp://ftp2.census.gov/geo/tiger/TIGER2018/ROADS/](ftp://ftp2.census.gov/geo/tiger/TIGER2018/ROADS/)
    * For every GEOID, unzip the roads shapefiles into the `Roads` folder.
    
1. Download and unzip the feature names shapefiles for each GEOID: 
    * [https://www2.census.gov/geo/tiger/TIGER2018/FEATNAMES/](https://www2.census.gov/geo/tiger/TIGER2018/FEATNAMES/)
    * For every GEOID, unzip the roads shapefiles into the `FeatNames` folder.
    
1. Run it!

1. Look at Boston.png output in `IndivRoads` folder
