# CryptoClustering
Module 19 Challenge : Unsupervised Machine Learning <br>
Contributor: Katy Yelle

## Challenge Background
This challenge uses python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

## Repository Structure
    -Main Folder
        -.gitignore
        -Cryto_Clustering.ipynb
        -README.md

    -Sub Folders
        -Resources
            -crypto_market_data.csv

        -images
            -composite_elbow_curves.png
            -composite_scatter_plots.png
            -market_data_plot.png
            -market_data_summary_stats.png
            -original_elbow.png
            -original_scatter.png
            -pca_elbow_curve.png
            -pca_scatter.png

## Overview & Analysis
#### Crypto_Currency.ipyng
First the file reads in the csv data and converts it to a dataframe.  The data is then examined with a summary statistics dataframe and a line plot. 

![Summary Stats](/images/market_data_summary_stats.png "Summary Stats") 

![Data Line Plot](/images/market_data_plot.png "Data Line Plot") 

The data is then prepared using standard scaler and setting the index to the coin ids. The resulting dataframe is then used to generate an elbow curve to determine the best value for k using the original data. 

![Original Elbow Curve](/images/original_elbow.png "Original Elbow Curve") 

Based on the elbow curve, the best value for k was determined to be 4. The file then runs a K-means with 4 clusters on the original data.  Then a scatter plot is generated with 24 hour price change percentage on the x-axis and 7 day price change percentage on the y-axis. 

![Original Scatter](/images/original_scatter.png "Original Scatter") 

Then clusters were optimized using a Principal Component Analysis with 3 components. The resulting total explained variance was about 89% (PC1: 37.1%, PC2: 34.7%, PC3: 17.6%). An elbow curve was then generated to determine the best value for k using the PCA data. 

![PCA Elbow Curve](/images/pca_elbow_curve.png "PCA Elbow Curve") 

Based on the elbow curve, the best value for k was determined to be 4, which was also the best value for k with the original data. 

![Composite Elbow Curves](/images/composite_elbow_curves.png "Composite Elbow Curves") 

A K-Means was then run in order to cluster the crypto currencies. A scatter plot was created with PC1 on the x axis and PC2 on the y axis. 

![PCA Scatter](/images/pca_scatter.png "PCA Scatter") 

The impact of using fewer features to cluster the data using K-Means is that the two larger clusters (represented in blue and red on the PCA Coin Clusters plot) are closer together compared to the original scatter plot where they are more spread out.  However both plots identified the same single point clusters (celsius-degree-token and ethlend) but the position of those single point clusters differs on the two plots.  For example, on the original plot the ethlend point is the most negative point along the x axis and at zero on the y axis.  However, on the PCA plot ethlend is the most positive point on the x-axis and the lowest point along the y axis (around -4)

![Composite Scatter](/images/composite_scatter_plots.png "Composite Scatter") 
