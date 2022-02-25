# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 4: West Nile Virus Prediction

# 1. Introduction

West Nile virus is the single-stranded virus that causes West Nile fever. West Nile virus can be transmitted to humans by the bite of an infected mosquito. It first emerged in the United States in the New York metropolitan area in 1999, and has since spread across the country.<sup>1</sup>

In Illinois, West Nile virus was first identified in September 2001 in the Chicago area. The following year, the state's first human cases and deaths from West Nile disease were recorded. By the end of 2002, Illinois had counted more human cases (884) and deaths (64) than any other state in the United States.<sup>1</sup>

By 2004, the City of Chicago and the Chicago Department of Public Health (CDPH) had established a comprehensive surveillance and control program that is still in effect today - a clear sign that the West Nile virus has become an endemic in Chicago

# 2. Problem Statement

Due to the endemic of West Nile Virus in Chicago, the Department of Public Health has set up a surveillance and control system through which weather, location, testing, and spraying data was collected. CDPH has contacted our team to develop a model to predict the locations where there would be West Nile virus outbreaks.

Using the datasets available, this model will help the City of Chicago and CPHD more efficiently and effectively target spraying of specific neighbourhoods with higher risk of West Nile Virus. This can help the City of Chicago save costs while still keeping the virus at bay. Our model efficacy will be assessed by the Kaggle submission.

Please note that there are 3 files to this project.
- 1.Problem Statement, Data Cleaning and EDA
- 2.Feature Engineering and Modelling
- 3.Cost Benefit Analysis & Conclusion


### Datasets
* [`train.csv`](./assets/train.csv): Training set for training the model
* [`test.csv`](./assets/test.csv): Test set for testing the model accuracy
* [`weather.csv`](./assets/weather.csv): Weather set to complement the training set
* [`spray.csv`](./assets/spray.csv): Spray set to indicate the spray info to complement the training set
* [`sampleSubmission.csv`](./assets/sampleSubmission.csv): Sample set referenced for the Kaggle submission.
* [`mapdata_copyright_openstreetmap_contributors.txt`](./assets/mapdata_copyright_openstreetmap_contributors.txt): Map data for the WNV areas


## Data Dictionary

|Feature|Dataset|Type|Description|
|---|---|---|---|
|id|test_final|int|ID number of the record|
|species|train_final/test_final|float|Mosquito species in trap|
|latitude|train_final/test_final|float|Latitude retrieved from GeoCoder|
|longtitude|train_final/test_final|float|Longitude retrieved from GeoCoder|
|month|train_final/test_final|int|month of the WNV test is performed|
|week|train_final/test_final|int|week of the WNV test is performed|
|day|train_final/test_final|int|day of the WNV test is performed|
|tmax|train_final/test_final|float|maximum daily temperature (F)|
|tmin|train_final/test_final|float|minimum daily temperature (F)|
|tavg|train_final/test_final|float|average daily temperature (F)|
|dewpoint|train_final/test_final|float|average dewpoint (F)|
|wetbulb|train_final/test_final|float|average wet bulb|
|heat|train_final/test_final|float|heating degree days|
|cool|train_final/test_final|float|cooling degree days|
|preciptotal|train_final/test_final|float|total daily rainfall (inch)|
|stnpressure|train_final/test_final|float|average atmospheric pressure (inch Hg)|
|sealevel|train_final/test_final|float|average sea level pressure (inch Hg)|
|resultspeed|train_final/test_final|float|resultant wind speed (mph)|
|resultdir|train_final/test_final|float|resultant wind direction (degrees)|
|avgspeed|train_final/test_final|float|average wind speed (mph)|
|cluster_0 to cluster_37|train_final/test_final|uint8|38 clusters base on trap location and numbers of mosquitos|


## Cost-Benefits analysis

The cost benefit analysis will measure the cost of conducting regular spray exercise versus the cost of hospitalisation and lost productivity of West Nile Virus cases.


### Annual Cost of Spraying

Key assumptions:
- Zenivex costs \$0.92/acre
- Pest control worker earns $20/hour
- 8pm - 1am (5 hour spray window)
- 149 traps - all will have spray operations
- 1 worker per trap
- 1km radius spray per trap
- Spray will be 7 times a year

With these assumptions, the annual cost of spraying is **\$84,0114.38**.


### Annual Cost of Hospitalisation and Lost Productivity

Key assumptions:
- All cases are non-severe
- Mean cost for non-severe cases - \$7,500
- 200 additional cases if no spray conducted

With these assumptions, the annual cost of hospitalisation and lost productivity is **\$1,500,000**.

As can be seen, conducting regular spraying operations will save Chicago an estimated **\$659,885.62** annually.


## Conclusion and Recommendations

Using the given dataset, we analysed the number of WNV cases in Chicago, the clustering traps for mosquito, location of the pesticide spraying, the impact of pesticide spraying vs the WNV outbreak, location with high mosquito count and WNV cluster and effect of weather on the number of mosquito and WNV. Based on our findings, we discovered some useful insights about how the features contributed to the outbreak of West Nile Virus (WNV).

For instant, the feature 'month' gives a significant indicator in relationship with the number of WNV cases which indicated that the highest numbers of WNV present mostly appeared during the month of July, August and September. This could be due to July to September being the summer period for Chicago.

Based on the scores returned from Pycaret, the best model is Light Gradient Boosting Machine with highest AUC score 0.8260. The higher the AUC score, the better the model's performance at distinguishing between the positive and negative classes.

### Further Research

We suggest to expand the study to other states and establish better insight on the number of mosquitos caught per trap, the life cycles of the mosquito and the weather pattern as to how, when and where to get a better predict target spraying model.

### Better Adoption

Despite of spraying the pesticide, the best way to prevent WNV disease is to reduce the number of mosquitos around the home and to take personal precautions to avoid mosquito bites. Precautions include:
  * change water in vases/bowls on alternate days
  * turn over all water storage containers
  * remove water from flower pot plates on alternate days
  * cover bamboo pole holders when not in use.
  * clear blockages and put BTI insecticide in roof gutters monthly
  * spray insecticide in the dark corner around the house
  * apply insect repellent and wear covered clothes

### Drone used in mosquito control

Recommend the use of drones in mosquito control with surveillance of nuisance mosquitos and potential vectors of pathogens. The insecticide application using drone to conduct surveillance and control in remote areas that are difficult to reach have been carried out by the GDG drone under the nuisance-reduction programme. The project was completed to nearly one thousand hectares of area producing mosquito larvae.

- [Source](https://sensorsandsystems.com/west-nile-virus-and-mosquito-nuisance-prevention-with-a-uav/?utm_source=rss&utm_medium=rss&utm_campaign=west-nile-virus-and-mosquito-nuisance-prevention-with-a-uav): West Nile Virus and Mosquito Nuisance Prevention with a UAV | Sensors and Systems
- [Source](https://www.terminix.com/blog/science-nature/drones-in-mosquito-control/): Mosquito Drone Technology | Terminix
