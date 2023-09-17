# Dataset: [Crime In Baltimore](https://www.kaggle.com/datasets/sohier/crime-in-baltimore)

## About Dataset
This dataset provides information about the crimes commited in Baltimore city. This dataset is accessible from the link provided above. The dataset covers crimes commited in the city between the years 2016-2020.

This project consists of 6 parts:
1. Introduction
2. Data Cleaning
3. Data visualization
4. Data Preprocessing
5. Modeling
6. Inference
7. Conclusion

# 1. Introduction

This data consists of total 15 columns and 2,76,529 observations.

## Attribute description:
* **CrimeDate:** Date of committed crime
* **CrimeTime:** Time of Committed crime
* **CrimeCode:** A unique code assigned to crime based of crime type and weapon used
* **Location:** Location of commited crime
* **Inside/Outside:** Flag shows whether crime was commited inside the house or not
* **Weapon:** Description of weapon used in crime
* **Post:** Code of nearby police station
* **District:** District of location of committed crime
* **Neighbourhood:** Neighborhood of place of incident
* **Longitude:** longitude of location of committed crime
* **Latitude:** latitude of location of committed crime
* **Location 1:** tuple of consisting longitude and latitude
* **Premise:** Premise
* **Total incidents:** No. of incident in a crime

# 2. Data Cleaning

There are **1,80,952 cells** which are **null** in the weapons column. This makes around **65% rows** of the whole data.
Dropping this rows can lead to loss of much significant data, which can reduce the quality of the dataset.

To deal with this null values, we can look at some other attributes, which can be related to this attribute. Like, *Crime type* can help to determine which type of weapon is used in a perticular crime.

## Crime type details:

* **Arson:** the criminal act of deliberately setting fire to property.
* **Assault by threat:** a threat or attempt to inflict offensive physical contact or bodily harm on a person that puts the person in immediate danger of or in apprehension
* **Auto theft:** the criminal act of stealing or attempting to steal a motor vehicle
* **Burglary:** llegal entry of a building with intent to commit a crime, especially theft.
* **Larceny:** theft of personal property
* **Rape:** to force someone to have sex when they are unwilling, using violence or threatening behaviour
* **Robbery:** the action of taking property unlawfully from a person or place by force or threat of force

It is observed that where ever weapon values are not available, the associated crime types are mostly:
1. Robbery
2. Theft
3. Arson
4. Larceny

In these types of crime most of the time there are not any weapon involved in crime.

So, the blank cells in weapon cells doesn't indicate that the data is missing, but we can conclude that *there could no weapons involved in the crime at the first place*.

So, we can fill all this blank cells with the "No weapon" value.

In the 'Total Incident' columns all the entries are filled with value 1. Which does not provide any value to the dataset. So, there is no loss in dataset quality in dropping this columns.
