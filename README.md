# Vehicle Resale Value Prediction
Building Regression Model to predict resale value of used cars

# Importance
Used cars sales are on a global increase due to the increased price of new cars and the incapability of customers to buy new cars due to the lack of funds. So, there is need for a used car price prediction system to effectively determine the worthiness of the car using a variety of features.
To be able to predict used cars market value can help both buyers and sellers. 

# Data Origin
The data used in this project was downloaded from Kaggle. The DataSet contains offerings of used cars in germany (20 attributes, 371528 examples). These cars where submitted to the website 'ebay Kleinanzeigen' and have been crawled between 2016-03-05 and 2016-04-07.

![](/images/data_info.PNG)

# Data Cleaning and Exploratory Data Analysis

* For cleaning purposes, inspected each column and removed undesired rows to counteract the data-distortion.
* 'seller', 'offerType','nrOfPictures','name','dateCrawled','dateCreated','lastSeen','postalCode' columns are found no impact on the target and are dropped from the dataset.
* Removed Outliers and bad data from the columns - 'yearOfRegistration','powerPS','price' 
<p float="left">
  <img src="/images/yearVprice_w_outliers.PNG" width="40%" height="300" />
  <img src="/images/yearVprice_wo_outliers.PNG" width="40%" height="300" /> 
</p>

<p float="left">
  <img src="/images/powerpsVprice_w_outliers.PNG" width="40%" height="300" />
  <img src="/images/powerpsVprice_wo_outliers.PNG" width="40%" height="300" /> 
</p>

* Missing data in columns 'notRepairedDamage', 'model','fuelType' is replaced with mode.
* On domain level, 'gearbox' varies with brand and 'vehicleType' varies with 'fuelType'. Missing data in these columns is replaced with modes of that respective groups. 
![](/images/brandVgearbox.PNG)
![](/images/fueltypeVvehicletype.PNG)

The shape of cleaned data turned out to be 318081 samples with 12 features(5-numerical and 7-categorical) and no missing data.
<p> Correlation values justified the relation of features with target. </p>

![](/images/heatmap.PNG)

# Data preprocessing
* Categorical columns are encoded with the help of LabelEncoder.
* StandardScaler is applied to scale the data

# Model Building
Post testing various Regression algorithms (linear Regression, SVR, XGboost), found Random Forest Regressor is best suited for the dataset. 

# Results
* ##### r2-score: 90.09062451445848
* ##### RMSE: 2152.478332372957
* ##### MAE: 1147.5807432474696

# Limitations
* There could be more features added that can be good predictors.
* Secondly, Gathering more data can yield more robust predictions. 
* Thridly, data cleaning process can be done more rigorously with the help of more technical information that helps to fill missing values more meaningfully.


