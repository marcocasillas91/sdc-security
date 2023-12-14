# Datalab Social Data Challenge Project
## Problem to analize: Insecurity in Mexico
This repo contains information about the project, which will consist on using public and private data 
to analize the crime problem in Mexico. 

We will be choosing a more specific approach with time in terms of location and issue, and will
base our work in the Agent-Based Modeling technique to understand the interaction of Agents and 
Environment that are involved on this topic.

We also expect to use Machine Learning in order to predict some criminal behaviour or to find patterns in data.


## EDA Visualizations 

From the reported crimes public dataset, visualizations were created in an Exploratory Data Analysis(EDA):

![calmap](https://github.com/marcocasillas91/sdc-security/assets/29104670/805a97df-e5a4-4038-967e-e0a037582e96)

The image above shows the robbery from passerby frequency in Cuauhtémoc alcaldia from 2018 to 2023. From this image it is possible to understand that there were more reported crimes in 2019, but this behavior is likely to be caused by less people reporting crimes due to COVID-19 ( less people in the streets and/or less people willing to  make a crime report).


![top10-colonias3-normalized-afternoon](https://github.com/marcocasillas91/sdc-security/assets/29104670/ada4a249-0d1a-464e-8cec-d28758a801f6)

The image above shows crime frequency in the 10 neighborhoods with more reported crimes, as well as the time of the day proportion of crimes.  


![Quarter year transeuntes2](https://github.com/marcocasillas91/sdc-security/assets/29104670/c9eef154-a9d9-4b53-a000-7a6ea58dcc7b)

The image above shows the robbery from passerby frequency in Cuauhtémoc alcaldia from 2018 to 2023 presented in quarters.



## Experiments


The information was consolidated to create two types of datasets: the first used the location of each robbery 
against a pedestrian within the alcaldia Cuauhtémoc, while the second is based on map locations 
with a fixed distance between them: a grid.


### First experiment/Dataset: Reported crimes
![cams_metro_patrullaje](https://github.com/marcocasillas91/sdc-security/assets/29104670/cbbe27c1-f39d-4de5-88c3-362615accd8d)

In the first scenario, we collected crime information, as well as the location of
main roads, patrol areas, metro stations and system video surveillance cameras
C5 using the geolocation software QGIS. The following image shows a combination of
layers with this information.


Heatmaps were created using the aforementioned data in a geolocoation software called QGIS. 
The software used the KDE ‘Kernel Density Estimation’ algorithm to create heatmaps using the location of
a point as a base and searching for similar points within a pre-established radius. In other words, 
this algorithm is based on the density of existing points to calculate the probability of appearance 
of new points.

The density of crime incidence in the location where each robbery happened was analyzed by counting the number of reported robberies in the surrounding area. 
Visualizations were created to show the change in crime frequency and displacement of crime hot spots.
By doing this, areas with reported high crime incidence could be identified, as well as analyzing if a seasonality behavior could be detected.

![18-22 transeunte max 105](https://github.com/marcocasillas91/sdc-security/assets/29104670/ed6991f0-289c-4826-bd78-61cd84e67465)

# Dataset columns

### Reported crimes dataset

**Number of rows: 61,886**

- **id:** Crime Victim ID 
- **idcarpeta:** Reported crime ID
- **delito:** Crime reported
- **categoria:** Type of crime
- **colonia:** Neighborhood
- **sexo_fem:** Victim of the crime is Female (1/0) 
- **edad:** Age
- **anio_hecho:** Year of the reported crime	
- **mes_hecho:** Month of the reported crime
- **fecha_hecho:** Date of the reported crime
- **hora_hecho:** Time of the reported crime
- **quarter:** Quarter (1-4)	
- **hour_of_day:** Hour of the reported crime (0-23)
- **time_of_day:** Time of the day (MORNING/AAFTERNOON/EVENING/NIGHT)	
- **crimen_lat:** Latitude	
- **crimen_lon:** Longitude

 


### Second experiment/Dataset: Grid Analysis

In order to use a more predictable reference, two grids were drawn over alcaldía Cuauhtémoc: 
100 m and 500 m. It was possible to obtain the number of thefts around each intersection
as well as the presence of other elements to determine the situation of each portion
of land.
In this particular experiment, the robbery count was obtained for each quarter from 2019 to
2023. Information on the location of other variables was obtained with the objective of characterizing the
around each grid point. These variables were:

- Schools
- Hospitals and social assistance centers
- Nightclubs, bars and clubs
- Sport centers
- Museums

![gridsQgis](https://github.com/marcocasillas91/sdc-security/assets/29104670/4404a20d-ce51-4164-bb4b-14ea65bc7d68)



### Grid dataset
#### 500m

**Number of rows: 224**

- **id:** Reported crime id
- **lat:** Latitude
- **lon:** Longitude
- **metro_500:** Number of metro stations in a 500m perimeter around a reported crime
- **cams_500:** Number of security cams in a 500m perimeter around a reported crime
- **zonas_pat:** Number of patrol areas in a 500m perimeter around a reported crime
- **antro_500:** Number of dance clubs in a 500m perimeter around a reported crime
- **salud_500:** Number of healthcare centers in a 500m perimeter around a reported crime
- **museo_500:** Number of museums in a 500m perimeter around a reported crime
- **esc_500:** Number of metro stations in a 500m perimeter around a reported crime
- **depo_500:** Number of sports institutions in a 500m perimeter around a reported crime
- **g500_19q1:** Number of crimes reported 500m around grid intersections in 2019, quarter 1
- **g500_19q2:** Number of crimes reported 500m around grid intersections in 2019, quarter 2
- **g500_19q3:** Number of crimes reported 500m around grid intersections in 2019, quarter 3
- **g500_19q4:** Number of crimes reported 500m around grid intersections in 2019, quarter 4
- **g500_20q1:** Number of crimes reported 500m around grid intersections in 2020, quarter 1
- **g500_20q2:** Number of crimes reported 500m around grid intersections in 2020, quarter 2
- **g500_20q3:** Number of crimes reported 500m around grid intersections in 2020, quarter 3
- **g500_20q4:** Number of crimes reported 500m around grid intersections in 2020, quarter 4
- **g500_21q1:** Number of crimes reported 500m around grid intersections in 2021, quarter 1
- **g500_21q2:** Number of crimes reported 500m around grid intersections in 2021, quarter 2
- **g500_21q3:** Number of crimes reported 500m around grid intersections in 2021, quarter 3
- **g500_21q4:** Number of crimes reported 500m around grid intersections in 2021, quarter 4
- **g500_22q1:** Number of crimes reported 500m around grid intersections in 2022, quarter 1
- **g500_22q2:** Number of crimes reported 500m around grid intersections in 2022, quarter 2
- **g500_22q3:** Number of crimes reported 500m around grid intersections in 2022, quarter 3
- **g500_22q4:** Number of crimes reported 500m around grid intersections in 2022, quarter 4
- **g500_23q1:** Number of crimes reported 500m around grid intersections in 2023, quarter 1


#### 100m

**Number of rows: 5383**

- **id:** Reported crime id
- **lat:** Latitude
- **lon:** Longitude
- **metro_100:** Number of metro stations in a 100m perimeter around a reported crime
- **cams_100:** Number of security cams in a 100m perimeter around a reported crime
- **zonas_pat:** Number of patrol areas in a 100m perimeter around a reported crime
- **antro_100:** Number of dance clubs in a 100m perimeter around a reported crime
- **salud_100:** Number of healthcare centers in a 100m perimeter around a reported crime
- **museo_100:** Number of museums in a 100m perimeter around a reported crime
- **esc_100:** Number of metro stations in a 100m perimeter around a reported crime
- **depo_100:** Number of sports institutions in a 100m perimeter around a reported crime
- **g100_19q1:** Number of crimes reported 100m around grid intersections in 2019, quarter 1
- **g100_19q2:** Number of crimes reported 100m around grid intersections in 2019, quarter 2
- **g100_19q3:** Number of crimes reported 100m around grid intersections in 2019, quarter 3
- **g100_19q4:** Number of crimes reported 100m around grid intersections in 2019, quarter 4
- **g100_20q1:** Number of crimes reported 100m around grid intersections in 2020, quarter 1
- **g100_20q2:** Number of crimes reported 100m around grid intersections in 2020, quarter 2
- **g100_20q3:** Number of crimes reported 100m around grid intersections in 2020, quarter 3
- **g100_20q4:** Number of crimes reported 100m around grid intersections in 2020, quarter 4
- **g100_21q1:** Number of crimes reported 100m around grid intersections in 2021, quarter 1
- **g100_21q2:** Number of crimes reported 100m around grid intersections in 2021, quarter 2
- **g100_21q3:** Number of crimes reported 100m around grid intersections in 2021, quarter 3
- **g100_21q4:** Number of crimes reported 100m around grid intersections in 2021, quarter 4
- **g100_22q1:** Number of crimes reported 100m around grid intersections in 2022, quarter 1
- **g100_22q2:** Number of crimes reported 100m around grid intersections in 2022, quarter 2
- **g100_22q3:** Number of crimes reported 100m around grid intersections in 2022, quarter 3
- **g100_22q4:** Number of crimes reported 100m around grid intersections in 2022, quarter 4
- **g100_23q1:** Number of crimes reported 100m around grid intersections in 2023, quarter 1

 
### Machine Learning Models

Several experiments were carried out to measure the degree of error in the prediction of 2023, quarter 1 crimes using the mean square error
(MSE) with diverse regression models: Linear Regression (LR), Random Forest (RF), Support Vector Machine (SVM) and XGBoost. 
Python scripts were created and used in order to run each model so that the average mean squared error of the model could be calculated. Also, histograms showing these results 
were generated using the *Matplotlib* library. 

Some of the base parameters for these tests were:

- **Number of iterations for each model:** 300
- **Train/Test Split:** 80/20 (Train/Test)
- **Types of Tests**
  - MSE for Scaled dataset vs. MSE for Non-Scaled dataset
  - Use of Principal Component Analysis(PCA) for dimension reduction vs use of all variables
  - MIC (Maximal Information Coefficient) to look for the most significant variables
  - **Predictions:** Number of crimes (Crimes) and heatmap crime density value(samples)

For this particular analysis, the best predictions were obtained by using all the variables in the grid dataset



![05-RF_scaled_crimes_samples](https://github.com/marcocasillas91/sdc-security/assets/29104670/21c9f8cb-50a4-45ec-8e4d-3e08490274a1)

![07 SVM_300_crimesAndSamples](https://github.com/marcocasillas91/sdc-security/assets/29104670/c2d0ab28-110f-4f62-abbc-6cedf7556ecf)

![10-XGB_300_CrimesSamplesScaled](https://github.com/marcocasillas91/sdc-security/assets/29104670/72de8146-f356-4fd1-a1c2-f4fd79820f97)

![11-RF-Crimes-ScaledAndNotScaled](https://github.com/marcocasillas91/sdc-security/assets/29104670/9d45d0ad-da32-42a1-a0c3-f417c31788e5)


The best results (less average mean squared error) were obtained using a **Random Forest Regressor model**. However, it required a high execution time because of the high computational complexity of the algorithm and the large amount of columns used. Similar results were obtained when using *SVM* and *XGBoost* regression models.


## Combination with Agent-Based Modeling (ABM)

We tried an  interesting approach by creating a model of the patrol areas inside *alcaldia* Cuahtémoc combined with the Machine learning models predictions. The main objective was provide with a different patrol strategy to the Cuauhtémoc police department in order to reduce response times and to help them to provide a better service.

The **alcaldia** was divided into patro areas and 4 main patrol strategies were tested using moeling software **NetLogo**:
- Random patrol: Police circulates in a random way through the **alcaldia**
- Previous year patrol: Officer put special attention in locations that happened to be hotspots in the previous year.  
- Machine Learning approach: Polices focuses more on lacations that are predicted to be crime hotspots by Machine Learning models.
- Reactive approach: Officers focuses more on locations were recent crime ocurred.

After running several iterations, however, there was no significant improvement on the response times or a significant increase in the number of elements attending a crime. This bahaviour could be explained by different reasons:
- The collected data might not be enough to explain the crime pattern
- The response time might not be affected significantly by changing a patrol strategy because of the nature of the crime itself, for instance, crime does not decrease, but displaces to other areas
- Low rate of reported crimes vs. actual number of crimes
- The Agent-Based Model might not be fully taking advantage of the information provided or might not be the right approach.
- Lack of information about the outcome of each particular reported crime (punished/attended)


A lot of information was gathered and visualizations were created to understand it. However, as any data project, it is important to get the persons with the domain knowledge involved. This project has the potential to evolve if a more specific crime problem can be identified, since crime itself is a very complex topic. And even by doing so, the project has to understand who will be final users in order to have an impact. Adding domain knowledge to the project from the start could help narrow down the scope to a point were a very specific problem for a very specific user can be identified before the data gathering stages. 

   
# Sources
https://datos.cdmx.gob.mx/dataset/carpetas-de-investigacion-pgj-cdmx

https://datos.cdmx.gob.mx/dataset/ubicacion-acceso-gratuito-internet-wifi-c5

https://datos.cdmx.gob.mx/dataset/ubicacion-acceso-gratuito-internet-wifi-c5

https://datos.cdmx.gob.mx/dataset/lineas-y-estaciones-del-metro

https://www.datos.cdmx.gob.mx/id/dataset/zonas-de-patrullaje-2018

https://www.inegi.org.mx/app/mapa/denue/default.aspx
