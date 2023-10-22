# CryptoClustering

In this challenge, you’ll use your knowledge of Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

Prepare the Data
    - Find the Best Value for k Using the Original Scaled DataFrame
    - Cluster Cryptocurrencies with K-means Using the Original Scaled Data
    - Optimize Clusters with Principal Component Analysis
    - Find the Best Value for k Using the PCA Data
    - Cluster Cryptocurrencies with K-means Using the PCA Data
 
Part_1_find the best K vlue base on the original data: 

  First we created the scaled data frame with the same index as the original data frame.
than, created a rage value of k and loop in it.
created a elbow data frame and plot this data frame to find out what is the best k value 
for the original data. 

Base on our first Elbow Curve, the best K value found using the original data in K=4.
 
-See image <elbow_original_data>

Part_2: Cluster Cryptocurrencies with K-means Using the Original Data
   - Initialize the K-Means model using the best value for k
   - Fit the K-Means model using the scaled data
   - Predict the clusters to group the cryptocurrencies using the scaled data
   - Add a new column to the DataFrame with the predicted clusters
   - Create a scatter plot using hvPlot by setting:
            - x="price_change_percentage_24h"` and `y="price_change_percentage_7d"`. 
            - Color the graph points with the labels found using K-Means. 
            - Add the crypto name in the `hover_cols` parameter to identify.
            - The cryptocurrency represented by each data point.
   
   -See image <scatter_original_data> for 3D see image < 3D_plot_original_data >


Part_3: Optimize Clusters with Principal Component Analysis
   
  - Create a PCA model instance and set `n_components=3`.
  - Use the PCA model with `fit_transform` to reduce to three principal components.
  - Retrieve the explained variance to determine how much information can be attributed to each principal component.

Total Explained Variance: 0.9132
Percentage of The Total Explained Variance:91%

  - Create a new DataFrame with the PCA data.
  - Copy the crypto names from the original data.
  - Set the coinid column as index.
  - Display sample data, see image <market_pca_df> 


Part_4: Find the Best Value for k Using the PCA Data

  - Create a list with the number of k-values from 1 to 11.
  - Create an empty list to store the inertia values.
  - Create a for loop to compute the inertia with each possible value of k
  - Create a dictionary with the data to plot the Elbow curve.
  - Create a DataFrame with the data to plot the Elbow curve.
  - Plot a line chart with all the inertia values computed with
     the different values of k to visually identify the optimal value for k.
 
 see image <Elbow-K-PCA Values>

Questions:
  
  * **Question:** What is the best value for `k` when using the PCA data?

  * **Answer:**  the best value for `k` when using the PCA data is 4


* **Question:** Does it differ from the best k value found using the original data?

  * **Answer:**  the best value for `k` when using the PCA is the same uwhen you use the original data.


Part_5: Cluster Cryptocurrencies with K-means Using the PCA Data

  - Initialize the K-Means model using the best value for k.
  - Fit the K-Means model using the PCA data.
  - Predict the clusters to group the cryptocurrencies using the PCA data.
  - Display sample data, see image <crypto_pca>
  - Create a scatter plot using hvPlot by setting 
           - x="PC1"` and `y="PC2"`. 
           - Color the graph points with the labels found using K-Means and 
           - Add the crypto name in the `hover_cols` parameter to identify the cryptocurrency represented by each data point.

See image <scatter_PCA_data>  

  I think it is better to create a 3D plot wheb we are having 3 components:

  see image < 3D_plot_PCA > for the 3D plot.


Part_6: Visualize and Compare the Results

The answer of the final question < After visually analyzing the cluster analysis results, what is the impact of using fewer features to cluster the data using K-Means?> 
is: 
 
     After examining the cluster analysis results visually, it appears that reducing the number of features used to cluster the data using K-Means had a significant impact. 
     In the initial plot, which depicted the original data clustering, the elbow curve indicated that the optimal value for K was 4, resulting in 4 clusters. 
     However, there were two clusters that only contained one data point each, and the other two clusters were not clearly separated. 
     By implementing PPCA and using the optimal value for K of 2, the resulting plot was more accurate and precise in clustering the data.