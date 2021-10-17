# Cryptocurrencies
<p align="center">
  <img width="200" height="200" src="https://github.com/jacquie0583/Cryptocurrencies/blob/main/Graphics/Image%207.jpg">
</p>

# Overview 
A prominent investment bank is interested in offering a new cryptocurrency investment portfolio for its customers. They’ve asked our company to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.
We had to process the dad to fit the machine learning models. Understanding there is no know output we made the decision to use unsupervised learning. To group the cryptocurrencies, the decision to use clustering algorithm was established. To demonstrate our analysis, we will use data visualizations to share the findings with the board.

# Three technical analysis and a written report.
1.	Preprocessing the Data for PCA

2.	Reducing Data Dimensions Using PCA

3.	Clustering Cryptocurrencies Using K-means

4.	Visualizing Cryptocurrencies Results

5.	An Analysis Report and a proposal for further statistical study

# Resources:

•	Data Source: crypto_data.csv

•	Data Tools: crypto_clustering_starter_code.ipynb.

•	Software: Python 3.9, Visual Studio Code 1.50.0, Anaconda 4.8.5, Jupyter Notebook 6.1.4 and Pandas

•	Libraries: SKLearn/Scikit-learn, Pandas, Plotly, Maptplotlib, hvPlot

•	Environment: Python 3.7

•	Unsupervised Machine Learning and Cryptocurrencies

•	Using Unsupervised Learning to Discover Unknown Patterns

# Supervised vs Unsupervised
Understanding the data and what can be done with it is an important first step before choosing an algorithm.  Unsupervised learning isn't the solution for every data analytic challenge. Supervised learning might not work for one situation doesn't mean unsupervised learning will work instead.
Unsupervised learning does not take in any pairing of input and outcomes from the data—it only looks at the data. This can cause some challenges when running the algorithm. Since we won't know the outcome it's predicting, we might not know that the result is correct.  This can lead to issues where we're trying to decide if the model has provided any helpful information that we can use to make decisions in the real world. For example, our store owner might run a model that ends up grouping the type of people by how much they're buying. This could be useful in some contexts—for example, knowing who the top spenders are—but it might not help the store owner better organize the store for maximum purchases per person, or understand the differences in product preferences between top purchasers.
The only way to determine what an unsupervised algorithm did with the data is to go through it manually or create visualizations. Since there will be a manual aspect, unsupervised learning is great for when you want to explore the data. Sometimes you'll use the information provided to you by the unsupervised algorithm to transition to a more targeted, supervised model.
As with supervised learning, data should be preprocessed into a correct format with only numerical values, null value determination, and so forth. The only difference is unsupervised learning doesn't have a target variable—it only has input features that will be used to find patterns in the data. It's important to carefully select features that could help to find those patterns or create groups.

#  Procedure/Results
I order to use unsupervised machine learning models on the data, the data needs to be processed to fit the machine learning models. There is no known output and the unsupervised ML is ideal for that type of analysis.
##  Step 1: Reprocessing the Data for PCA
### Data Selection
Before moving data to our unsupervised algorithms, complete the following steps for preparing data to avoid any errors and to ensure we are getting the right results.  Data selection entails making good choices about which data will be used. Consider what data is available, what data is missing, and what data can be removed. For example, say we have a dataset on city weather that consists of temperature, population, latitude and longitude, date, snowfall, and income. After looking through the columns, we can readily see that population and income data don't affect weather. We might also notice some rows are missing temperature data. In the data selection process, we would remove the population and income columns as well as any rows that don't record temperatures.
### Data Processing
Data processing involves organizing the data by formatting, cleaning, and sampling it. In our dataset on city weather, if the date column has two different formats—mm-dd-yyyy (e.g., 01-23-1980) and month-data-year (e.g., jan-23-1980)—we would convert all dates to the same format.
### Data Transformation
Data transformation entails transforming our data into a simpler format for storage and future use, such as a CSV, spreadsheet, or database file. Once our weather data is cleaned and processed, we would export the final version of the data as a CSV file for future analysis.

### Requirements for a useable dataset are as follows:
•	Null values and missing data: Unsupervised learning models can't handle null values or missing data.   Drop null or missing values or decide and drop the entire column.

•	Datatype: All data must be converted to numerical data type.

•	Duplicates: Remove duplicates, they aren't telling us anything new and can skew the results.

•	Scaled values: Data has been manipulated to ensure that the variance between the numbers won't skew the results. When features have different scales they can have disproportionate impact on the model. The unscaled value could lead to messy graphs. Therefore, it is important to understand when to scale and normalize data. For example, if four columns of data are single digits, and the fifth column is in the millions, we would need to scale the fifth column to align the other four.

## Results:
Crypto DataFrame looks like the image below prior to the “get_dummies() method” to create variables for the two text features, using the “StandardScaler fit_transform()” function to standardize the features.

<p align="center">
  <img width="600" height="300" src="https://github.com/jacquie0583/Cryptocurrencies/blob/main/Graphics/image%2010.jpg">
</p> 

Result after the fit and transforming

<p align="center">
  <img width="300" height="300" src="https://github.com/jacquie0583/Cryptocurrencies/blob/main/Graphics/image%2011.jpg">
</p> 

## Step 2: Feature Elimination, Feature Extraction & Reducing Data Dimensions using PCA
Having too many features in the dataset when working with unsupervised ML can cause overfitting. To avoid this, we can use the process of reducing features also known as dimensionality reduction. There are two options for coping with too many features: elimination and extraction.
Feature Elimination removes a good number of features so the model won't be run using every column.
Feature Extraction combines all features into a new set that is ordered by how well they predict our original variable.
PCA is statistical technique to sped up machine learning algorithms when the number of input features (or dimensions) is too high. PCA reduces the number of dimensions by transforming a large set of variables into a smaller one that contains most of the information in the original large set. The first step in PCA is to standardize these features by using the StandardScaler library. After the date has been standardized to use PCA to reduce the number of features (argument of n_components) to get a smaller set of dimensions called principal components. These new components are new main dimensions of variation that contain most of the information in the original dataset.
Explained Variance Ration tells us how much information can be attributed to each principal component: for example the first principal component contains 72.77% of the variance and the second contains 23.03%. Together, they contain 95.80% of the information.

## Results:
Image 12

<p align="center">
  <img width="600" height="300" src="https://github.com/jacquie0583/Cryptocurrencies/blob/main/Graphics/image%2012.jpg">
</p>


Cluster DataFrame looks like the image below:
Image 2

<p align="center">
  <img width="600" height="300" src="https://github.com/jacquie0583/Cryptocurrencies/blob/main/Graphics/image%202.jpg">
</p>

## Step 3: Clustering Cryptocurrencies Using K-means and finding the Best Value using Elbow Curve
•	Clustering is a type of unsupervised learning that groups data points together. K-means is an unsupervised learning algorithm used to identify and solve clustering issues. K represents how many clusters there will be. These clusters are then determined by the means of all the points that will belong to the cluster. The K-means algorithm groups the data into K clusters, where belonging to a cluster is based on some similarity or distance measure to a centroid. The centroid is found by taking the mean of all the x-values in the cluster, and the mean of all the y-values in a cluster. Elbow Curve is an easy method for determining the best number for K-means. To create the elbow curve, two values are needed - a list of K values and a list of inertia values. Loop through the 10 values for K, for example and determine the inertia: range (1, 11).
•	Inertia is one of the most common objective functions to use when creating an elbow curve. The inertia is measuring the amount of variation in the dataset. The inertia measuring the amount of variation in the dataset. Inertia is the objective function to plot K values against.
## Results:
## Elbow Curve

use the MinMaxScaler().fit_transform method to scale the "TotalCoinSupply" and "TotalCoinsMined" columns:

<p align="center">
  <img width="600" height="300" src="https://github.com/jacquie0583/Cryptocurrencies/blob/main/Graphics/image%2015.png">
</p>

Using the dataset and analysis we found that 4 clusters is the initial point.
By running an analysis using K=4 and applying the K-means algorithm, got the below results:

<p align="center">
  <img width="600" height="300" src="https://github.com/jacquie0583/Cryptocurrencies/blob/main/Graphics/image%2016.png">
</p


 
## Step 4: Visualizing Cryptocurrencies Results and Interpretation
 
•	Visualizing the clusters helps to graphically understand how they are arranged.

• 3D graph and PCA visualization for 3D visualization we used 3D scatter plot with Plotly Express. Three principal components (on x, y, and z             axis), that were created with PCA algorithm are plotted on the graph. These 3 components contains most of the information in the original large         data set. As we can see the form of the graph, cryptocurrency is clustered in 4 groups with similar characteristics. When we hover over the             specific element the graph shows label with Coin Name and its Algorithm.

• 2D visualization and correlation between Total Coins Supply and Total Coins Mined For 2D visualization I used hvPlot, a graphing library that          allows deeper exploration of the data. This graph has Total Coins Supply on y-axis and Total Coins Mined on x-axis. From the graph we can see          correlation between those two components. Different colors indicate different classes that crypto coins belong to. When we hover over the              specific element the graph shows labels with Coin Name and its Class.
 
 
## Results:
3D scatter plot using the Plotly Express scatter_3d():
<p align="center">
  <img width="600" height="300" src="https://github.com/jacquie0583/Cryptocurrencies/blob/main/Graphics/image%201.jpg">
</p>

<p align="center">
  <img width="600" height="300" src="https://github.com/jacquie0583/Cryptocurrencies/blob/main/Graphics/image%2020.png">
</p>
 
Table use the hvplot.table() function

<p align="center">
  <img width="600" height="300" src="https://github.com/jacquie0583/Cryptocurrencies/blob/main/Graphics/Image%2014.jpg">
</p>

Created an hvplot scatter plot with x="TotalCoinsMined", y="TotalCoinSupply", and by="Class", and have it show the CoinName when you hover over the the data point.  A 2D hvplot scatter plot with x="TotalCoinsMined_scaled", y="TotalCoinSupply_scaled", and by="Class" with the CoinName displayed.
Scatter plot should look similar to the image below:
 

<p align="center">
  <img width="600" height="300" src="https://github.com/jacquie0583/Cryptocurrencies/blob/main/Graphics/image%2017.png">
</p>

Class 2 and Class 3 are the same; Classes 0 and 1 gave out three different Classes: 0, 1, 4.
 
<p align="center">
  <img width="600" height="300" src="https://github.com/jacquie0583/Cryptocurrencies/blob/main/Graphics/image%2018.png">
</p> 

A table is created featuring the tradable cryptocurrencies using the hvplot.table().
image

<p align="center">
  <img width="600" height="300" src="https://github.com/jacquie0583/Cryptocurrencies/blob/main/Graphics/Image%2014.jpg">
</p>


With this new DataFrame, clustered_df , we start with a 3D Scatter plot using the Plotly Express scatter_3d() function to visualize the 4 Classes.
image

<p align="center">
  <img width="600" height="300" src="https://github.com/jacquie0583/Cryptocurrencies/blob/main/Graphics/image%2019.png">
</p>


