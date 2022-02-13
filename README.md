# unsupervisedML-challenge

For this week's homework assignment, unsupervised machine learning was used to explore whether the listed cryptocurrencies can be grouped. First, the CSV file for crpytocurrency data was read. As part of the cleaning process, columns that had even a single null value needed to be removed. The " .drop()" function was used to accomplish this. Additionally, the total coins mined column needed to be greater than 0 to only consider the valid values. The "Algorithm" and "Proof Type" columns had to be converted to numerical data by using the " .get_dummies()" function, and lastly, the data had to be scaled in order to avoid an inbalance or inaccurate results that would be derived from this clean dataset. 

An explained variance was applied to a PCA model in order to perform dimentionality reduction. 90% of variance had remained with less features, creating a total of 74 rows. In order to further reduce the dataset, a t-SNE model was performed, along with demonstrating its' corresponding model. Below is a screenshot of the code that can be found on the "crypto_data.ipynb" file.

![Screen Shot 2022-02-13 at 12 55 45 AM](https://user-images.githubusercontent.com/72631173/153742626-4743db74-24bd-4b30-be0c-cb3dc21b4634.png)

Although it may not be heavy data on one side, there seemes to be a clear division between different clusters. In order to confirm this, a K-Means model was performed. In doing a K-Means model, we are able to clearly identify the amount of clusters by using an Elbow Curve. The location in which the data begins to level out is the indication of the best amount of clusters that there is in the dataset. A "for loop" was created for a range of 1-10, representing the number of clusters. Basically, the data derived from the t-SNE model was used for this section, and it was iterated through this for loop to identify the number of clusters. A picture has been included to demonstrate how the Elbow Curve looked. 

![Screen Shot 2022-02-13 at 12 36 31 AM](https://user-images.githubusercontent.com/72631173/153742820-34fa9da0-ba69-4a6e-9f22-1893b27f8869.png)

Although it may have little to no effect, the cryptocurrencies can be grouped in 6 clusters. Based on the Elbow Curve, the data seems to leveling out around 6 clusters. This would include each individual point that is skewed towards the right, and the big cluster of data points towards the bottom left of the image. This may not be the best dataset for clustering, but we can visually see the values split in the scatter plot, shown in line 9 of the code. 
