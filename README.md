# Titanic-Spaceship : Project Overview
* Data Analysis of a Kaggle competition dataset Titanic Spaceship.
* This dataset is an ongoing competition on Kaggle.
* There are two different dataset for this competition one is traind_dataset and another one is test_dataset.
* https://www.kaggle.com/competitions/spaceship-titanic -- Dataset Link
* People are travelling in a Spaceship called Titanic and they are travelling from their Home Planet to the Destination Planet which are habitable exoplanets orbiting nearby stars carrying over 13000 passengers. But unfortunately while going through Alpha Centauri it's first destination the torrid 55 Cancri E - the Titanic Spaceship got collided with a spacetime anaomaly which was hidded in the cloud of dust. Due to this several passengers got transported to the different dimension.

# AIM
To find the how many passengers got transported to the different dimension.

# Resource Used
* Python : v3.8 Jupyter Notebook : v6.4
* **Packages** : Pandas : v1.4.3, Numpy : v1.23.0, Matplotlib : v3.5.2, Matplotlib-inline : v0.1.3, Seaborn : v0.10.1, Scikit-Learn : v1.1.1
* RandomForestClassifier Machine Learning Model used to get the high **Accuracy Score** and also done Hyperparameter tuning to get the best result using **RandomizedSearchCV**. 

# EDA (Exploratory Data Analysis)
# **Train_Dataset**
* Had to do some Data cleaning along with EDA to remove any unnecessary data or any null values as well as converting some of the categorical columns to numerical columns to apply the Machine Learning model.
* **Columns**
* PassengerId, HomePlanet, CryoSleep, Cabin, Destination, Age, VIP, RoomService, FoodCourt, ShoppingMall, Spa, VRDeck, Name, Transported
* The dataset have total of **8693 rows × 14 columns**. Dropped the Name column as it was not a required column for the analysis.

# Graphs
* Home Planet and Destination Planet on which humans wants to go.
![Home Planet and Destination Planet](https://github.com/sumeet860/Titanic-Spaceship/blob/main/histplot_titanic.png?raw=True "Home Planet and Destination Planet")

* People of different ages on the spaceship.
![Age](https://github.com/sumeet860/Titanic-Spaceship/blob/main/age_titanic.png?raw=True "Age")

* KDE plot of age to find out maximum number of people of certain age on the Spaceship.
![Age with kde plot](https://github.com/sumeet860/Titanic-Spaceship/blob/main/ages_titanic.png?raw=True "Age KDE plot")

* Checking the dataset if it contains any null values or not using numpy isnull() function and plotting it using sns.heatmap()
![Heatmap for null values](https://github.com/sumeet860/Titanic-Spaceship/blob/main/heatmap_titanic.png?raw=True "Heatmap for null values")

* As we can see there are lot of null values we will fill the null values with the median and mode of each columns.
* Then will change any categorical column to numerical column with LabelEncoder from Scikit-Learn.

# Correlation Matrix
![Correlation Matrix](https://github.com/sumeet860/Titanic-Spaceship/blob/main/correlation_matrix_titanic.png?raw=True "correlation matrix")


# **Test_Dataset**
* Had to do some Data cleaning along with EDA to remove any unnecessary data or any null values as well as converting some of the categorical columns to numerical columns to apply the Machine Learning model.
* **Columns**
* PassengerId, HomePlanet, CryoSleep, Cabin, Destination, Age, VIP, RoomService, FoodCourt, ShoppingMall, Spa, VRDeck, Name
* The dataset have total of **4277 rows × 12 columns**. Dropped the Name column as it was not a required column for the analysis.

# Graphs
* Home Planet and Destination Planet on which humans wants to go.
![Home Planet and Destination Planet](https://github.com/sumeet860/Titanic-Spaceship/blob/main/histplot1_titanic.png?raw=True "Home Planet and Destination Planet")

* People of different ages on the spaceship.
![Age](https://github.com/sumeet860/Titanic-Spaceship/blob/main/age1_titanic.png?raw=True "Age")

* KDE plot of age to find out maximum number of people of certain age on the Spaceship.
![Age with kde plot](https://github.com/sumeet860/Titanic-Spaceship/blob/main/ages1_titanic.png?raw=True "Age KDE plot")

* Checking the dataset if it contains any null values or not using numpy isnull() function and plotting it using sns.heatmap()
![Heatmap for null values](https://github.com/sumeet860/Titanic-Spaceship/blob/main/heatmap1_titanic.png?raw=True "Heatmap for null values")

* As we can see there are lot of null values we will fill the null values with the median and mode of each columns.
* Then will change any categorical column to numerical column with LabelEncoder from Scikit-Learn.

# Correlation Matrix
![Correlation Matrix](https://github.com/sumeet860/Titanic-Spaceship/blob/main/correlation_matrix1_titanic.png?raw=True "correlation matrix")


# **Machine Learning**

* Splitting the data into train and test model. Have to find how many got transported so assigning transported column to 'y' and other columns to 'X'.
* Using the **RandomForestClassifier()** from scikit-learn.ensemble.
* Modelling with the following parameters random_state = 1, n_estimators = 10, min_samples_split = 2.
* The accuracy score tha we get is approx 79%.

**Hyperparameter Tuning using RandomizedSearchCV**

* Doing the hyperparameter tuning to improve the accuracy score.
* Using the following parameters to improve the score { "n_estimators": np.arange(10, 1000, 50), 
"max_depth": [None, 3, 5, 10], 
"min_samples_split": np.arange(2, 20, 2), 
"min_samples_leaf": np.arange(1, 20, 2) }

* The best parameter according to RandomizedSearchCV are {'n_estimators': 310,
 'min_samples_split': 12,
 'min_samples_leaf': 5,
 'max_depth': None}
 
 * After hyperparameter tuning the accuracy score improved from 0.792 (79.2%) to 0.814 (81.4%).
 
 # Submission
 * Saving the data into submission.csv file.
