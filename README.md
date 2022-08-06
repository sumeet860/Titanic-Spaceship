# Titanic-Spaceship : Project Overview
* Data Analysis of a Kaggle competition dataset Titanic Spaceship.
* This dataset is an ongoing competition on Kaggle.
* https://www.kaggle.com/competitions/spaceship-titanic -- Dataset Link
* People are travelling in a Spaceship called Titanic and they are travelling from their Home Planet to the Destination Planet which are habitable exoplanets orbiting nearby stars carrying over 13000 passengers. But unfortunately while going through Alpha Centauri it's first destination the torrid 55 Cancri E - the Titanic Spaceship got collided with a spacetime anaomaly which was hidded in the cloud of dust. Due to this several passengers got transported to the different dimension.

# AIM
To find the how many passengers got transported to the different dimension.

# Resource Used
* Python : v3.8 Jupyter Notebook : v6.4
* **Packages** : Pandas : v1.4.3, Numpy : v1.23.0, Matplotlib : v3.5.2, Matplotlib-inline : v0.1.3, Seaborn : v0.10.1, Scikit-Learn : v1.1.1
* RandomForestClassifier Machine Learning Model used to get the high **Accuracy Score**

# EDA (Exploratory Data Analysis)
* Had to do some Data cleaning along with EDA to remove any unnecessary data or any null values as well as converting some of the categorical columns to numerical columns to apply the Machine Learning model.
* **Columns**
* PassengerId, HomePlanet, CryoSleep, Cabin, Destination, Age, VIP, RoomService, FoodCourt, ShoppingMall, Spa, VRDeck, Name, Transported
* The dataset have total of **8693 rows × 14 columns**. Dropped the Name column as it was not a required column for the analysis.

# Graphs
![Home Planet and Destination Planet](https://github.com/sumeet860/Titanic-Spaceship/blob/main/histplot_titanic.png?raw=True "Employee Data title")
