# Project Title
**DataSet Source:**  https://www.kaggle.com/harlfoxem/housesalesprediction/data
This dataset contains house sale prices for <b>King County</b>, which includes Seattle. It includes homes sold between May 2014 and May 2015.It's a great dataset for evaluating simple regression models.
About the Data Set:
id - Unique ID for each home sold 

date - Date of the home sale 

price - Price of each home sold 

bedrooms - Number of bedrooms 

bathrooms - Number of bathrooms, where .5 accounts for a room with a toilet but no shower 

sqft_living - Square footage of the apartments interior living space 

sqft_lot - Square footage of the land space 

floors - Number of floors 

waterfront - A dummy variable for whether the apartment was overlooking the waterfront or not 

view - An index from 0 to 4 of how good the view of the property was 

condition - An index from 1 to 5 on the condition of the apartment, 

grade - An index from 1 to 13, where 1-3 falls short of building construction and design, 7 has an average level of construction and design, and 11-13 have a high quality level of construction and design. 

sqft_above - The square footage of the interior housing space that is above ground level 

sqft_basement - The square footage of the interior housing space that is below ground level 

yr_built - The year the house was initially built 

yr_renovated - The year of the house’s last renovation 

zipcode - What zipcode area the house is in 

lat - Lattitude 

long - Longitude 

sqft_living15 - The square footage of interior housing living space for the nearest 15 neighbors 

sqft_lot15 - The square footage of the land lots of the nearest 15 neighbors 

## Getting Started

First, we carry out an exploratory analysis of the data.Next we compute a few new values from the variables in the data set. For instance, we’re interested in finding out siginficant predictors in predicting price. First we do basic data wrangling and then try to null and full model to see reltionship. After this we continue with the data set to do linear models.

### Prerequisites

We need the following major libraries in R to work with the data set:

```
library(lubridate)
library(GGally)
library(ggplot2)
library(hydroGOF)
library(mvtnorm)
library(tidyverse)
library(stringr)
library(lubridate)
library(DT)
library(caret)
library(leaflet)
library(corrplot)
library(boot)
```


## Running the queries

Running the linear model with top 10 predictors

```
lm4<-lm(price~ ( grade + zipcode + sqft_living + waterfront + view + condition + 
    year + yr_renovated + sqft_above + bedrooms:bathrooms ),data=df)
summary(lm4)
```

ploting the tree

```
library(rpart)
library(rpart.plot)
regTree <- rpart(price ~ .+ sqft_living + zipcode + waterfront + view + yr_built+yr_renovated + bedrooms+bathrooms + sqft_above + condition +floors, data= df, method = "anova")
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone who's code was used
* Inspiration
* etc
