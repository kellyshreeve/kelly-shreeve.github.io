## Global Route Optimization

<p align="center">
  <img src="/images/route-optimization/optimized-route.png?raw=true" 
  width="600"
  height="300"
  alt="Map using geo-location data to display an optimized route around the world">
</p>

Geo-location data was used to map and optimize a route around the world. I found, obtained, and cleaned a geo-location data set then used the data to visualize and optimize the global route in Python. 

I passed the optimized solution to software engineers who integrated it into a webpage. The results is a well-designed site where users can find and interact with a data science solution that won first place in the Jingle Bell Code Jam, December 2023.

#### Live

<a href="https://skovakina.github.io/jingle-bells-jam/" target="_blank">Our project live</a>

#### Data Set

A data set of longitude and latitudes for each country around the world was found open-source on Kaggle and can be accessed [here](https://www.kaggle.com/datasets/alexkaechele/country-geo). 

country.csv

* *country*: country abbreviation
* *latitude*: country latitude
* *longitude*: country longitude
* *name*: country name

The dataset contains information on country abbreviation, latitude, and longitude for 245 countries around the world. The data were explored for missing values, duplicates, and incorrect values. Only one missing value was found, and it was dropped from the data. Data were otherwise in good condition and ready for analysis.

#### Approach

This problem is a take on the 'Traveling Sales Man' problem to optimize the route between multiple locations.  

Concorde library in Python optimizes the route between many locations, with quick and efficient calculations.  

*Haversine* distance to calculates 'as the bird flies' while taking into account the curvature of the earth.

#### Random Model

First, a random model was fit as a baseline to find distance and time it would take Santa without data. This model chooses the next city randomly (if santa chose off vibes), and calculates the Haversine distance along the random route:

<p align="center">
  <img src="/images/route-optimization/random-route.png?raw=true" 
  width="600"
  height="300"
  alt="Map using geo-location data to display an optimized route around the world">
</p>

**Random Route Results**: 

Random Start city: Antarctica

Random Route Order: 'Antarctica', 'France', 'Australia', 'Bolivia', 'United States', 'Greenland', 'Afghanistan', 'Russia', 'Central African Republic'

Random Route Distance: 46977.53 miles

Random Route Time: 36.14 Hours

#### Optimized Model

With Concorde library, Santa's route was optimized to the shortest distance possible. This library was developed specifically to solve the Traveling Sales Man problem and can quickly and efficiently solve the best route between locations:

<p align="center">
  <img src="/images/route-optimization/optimized-route.png?raw=true" 
  width="600"
  height="300"
  alt="Map using geo-location data to display an optimized route around the world">
</p>

**Optimized Route Results**:

Optimal Start city: Afghanistan

Optimized Route Order: 'Afghanistan', 'Russia', 'Australia', 'Antarctica', 'Bolivia', 'United States', 'Greenland', 'France', 'Central African Republic'

Optimal Distance: 31087 miles

Optimized Time: 23.91 hours

Time to Calculate Solution: 0.03 seconds

#### Conclusions  

Santa has a big night ahead of him, delivering presents around the globe. Merry Mailers wants to help him optimize his trip! To create a model of his trip, nine locations were chosen from around the world: United States, Bolivia, Greenland, Antarctica, France, Central African Republic, Afhanistan, Russia, and Australia.  

First, a random route was chosen as a baseline (if santa chose his next location off vibes). In his sub-optimal route, santa had to travel 50,000 miles and needed 35 hours to make it around the world. He wouldn't have made it in time!  

With Merry Mailer's specialized route optimization algorithm, we were able to take santa's trip down to 31,000 miles and just under 24 hours. This algorithm used state-of the art Concorde library and Haversine distance to minimize santa's distance delivering from one house to another and speedily found an optimal solution in 0.03 seconds! We're taking the pressure off santa by telling him to travel in this order: Afghanistan, Russia, Australia, Antarctica, Bolivia, United States, Greenland, France, Central African Republic. With our modeling sofware, santa save 20,000 miles and can feel good about making it everywhere he needs to go.  

What's next for Merry Mailers? We're committed to follow up with each of our clients. We'll measure santa's success this season, and maybe add some more locations into our optimizer for next year. And it looks like we'll be staying busy through the year - the Easter Bunny, St. Nicholas, and Tooth Fairy have been knocking at our door.