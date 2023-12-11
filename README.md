# Datalab Social Data Challenge Project
## Problem to analize: Insecurity in Mexico
This repo contains information about the project, which will consist on using public and private data 
to analize the crime problem in Mexico. 

We will be choosing a more specific approach with time in terms of location and issue, and will
base our work in the Agent-Based Modeling technique to understand the interaction of Agents and 
Environment that are involved on this topic.

We also expect to use Machine Learning in order to predict some criminal behaviour or to find patterns in data.

## Experiments

The information was consolidated to create two types of datasets: the first used the location of each robbery 
against a pedestrian within the alcaldia Cuauhtémoc, while the second is based on map locations 
with a fixed distance between them: a grid.


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