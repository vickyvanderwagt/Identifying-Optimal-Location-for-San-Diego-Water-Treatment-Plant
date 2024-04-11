# ADS508-Final_Project
Class: Data Science with Cloud Computing at University of San Diego

### Optimal Locations for Water Treatment Facility in San Diego County
Water parameters were analyzed from samples across San Diego county. Samples were classified into acceptable or not acceptable levels for drinking water. Data was used to find the 10 best cluster centers to recommend locations for water treatment plants, based on areas with the highest density of acceptable parameter measures. 

Each of the analyzed paramters has a specified acceptable range in the code. These ranges can be manipulated. 

Parameters used and default acceptable ranges:
* Conductance      | 50-800 uS/cm
* Dissolved Sodium | 20-200 mg/L
* Total alkalinity | 100-300 mg/L as CaCO3
* Dissolved calcium| 0-200 mg/L
* pH               | 6.5-8.5 pH units

### Process
Data was retrieved from https://catalog.data.gov/dataset/water-quality-data-c4036, saved into AWS S3 bucket *ads508group4finalproject*. Data was manipulated in AWS Sagemaker studio, and Athena was used to make a database to relate sample locations to lab results. A DBSCAN model was then generated to find cluster centers containing the highest density of acceptable water measurements.

### Result
The map below specifies the 10 recommended water treatment facility locations. Assessing viability was not within scope of this project. 

<img width="950" alt="Most optimum location on water quality San Diego" src="https://github.com/vickyvanderwagt/ADS508-Final_Project/assets/116703243/a45559dc-f02b-4e09-ae56-b4c8be8dbafd">

### Limitations
* Many samples were missing measurements for parameters. Therefore, data was filtered for the most commonly measured parameters. All samples missing measurements from these parameters were excluded from analysis.
  
* Due to relatively low number of samples containing measurements for all chosen paramters, data from 1950s and onwards was included. Water composition could have changed since then.
  
* The DBSCAN model selected locations with the highest density of acceptable water samples; however, this could bias the model towards areas with more water measurements.
  
### Contributors: 
* Landon Padgett
* Parisa Kamizi
* Vicky van der Wagt

