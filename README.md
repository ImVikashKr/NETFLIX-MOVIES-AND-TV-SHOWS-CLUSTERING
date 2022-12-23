# NETFLIX-MOVIES-AND-TV-SHOWS-CLUSTERING
This dataset consists of tv shows and movies available on Netflix as of 2019. The dataset is collected from Flixable which is a third-party Netflix search engine.  In 2018, they released an interesting report which shows that the number of TV shows on Netflix has nearly tripled since 2010. The streaming service’s number of movies has decreased by more than 2,000 titles since 2010, while its number of TV shows has nearly tripled. It will be interesting to explore what all other insights can be obtained from the same dataset.  Integrating this dataset with other external datasets such as IMDB ratings, rotten tomatoes can also provide many interesting findings.

# Problem Statement:
This dataset consists of tv shows and movies available on Netflix as of 2019. The dataset is collected from Flixable which is a third-party Netflix search engine.
In 2018, they released an interesting report which shows that the number of TV shows on Netflix has nearly tripled since 2010. The streaming service’s number of movies has decreased by more than 2,000 titles since 2010, while its number of TV shows has nearly tripled. It will be interesting to explore what all other insights can be obtained from the same dataset.
Integrating this dataset with other external datasets such as IMDB ratings, rotten tomatoes can also provide many interesting findings.

In this project, you are required to do
1. Exploratory Data Analysis
2. Understanding what type of content is available in different countries
3. Is Netflix increasingly focusing on TV rather than movies in recent years?
4. Clustering similar content by matching text-based features
Based on the attributes related to the Tv shows or movies, we will be implementing diﬀerent clustering algorithms which come under the unsupervised Machine learning category.

# Data Cleaning:
Prior to EDA, cleaning the data is essential since it will get rid of any ambiguous information that can have an impact on the results.

director, cast, country, date_added, and rating columns have missing or null values. I have replaced all the null values of the columns with ‘Not Known’.

I removed the show id column because it doesn't offer any useful information.

# Steps involved:
●	Exploratory Data Analysis 
Exploratory Data Analysis refers to the critical process of performing initial investigations on data so as to discover patterns, to spot anomalies, to test hypothesis and to check assumptions with the help of summary statistics and graphical representations.

●	Null values Treatment
director, cast, country, date_added, and rating columns have missing or null values. I have replaced all the null values of the columns with ‘Not Known’.

# Algorithms:
TF-IDF: Term Frequency, Inverse Document Frequency. It indicates the significance/relevance of a word in a corpus.  Term Frequency represents the number of instances of a given word and inverse document frequency tests how relevant the word is.

PCA: PCA is a dimensionality reduction technique. In this principal component are computed, and a lot of information is also retained. The graph shows the explained variance value for the different number of PCA components. n_components 4000 was chosen in this project.

Textual data were combined and converted into numerical data using TF-IDF.  Applied PCA to perform dimensionality reduction. Data were converted to 4000-dimensional data. K-Means is used in this project.

1.	K-Means Clustering
K-means algorithm identifies k number of centroids, and then allocates every data point to the nearest cluster, while keeping the centroids as small as possible.
To process the learning data, the K-means algorithm in data mining starts with a first group of randomly selected centroids, which are used as the beginning points for every cluster, and then performs iterative (repetitive) calculations to optimize the positions of the centroids
It halts creating and optimizing clusters when either:
The centroids have stabilized — there is no change in their values because the clustering has been successful.
The defined number of iterations has been achieved.
![image](https://user-images.githubusercontent.com/33064867/209317792-80c890ff-1b8b-49c1-9a5d-33a770576f6e.png)

2.	Gaussian Clustering
Gaussian mixture models can be used to cluster unlabeled data in much the same way as k-means. There are, however, a couple of advantages to using Gaussian mixture models over k-means.
a Gaussian mixture model involves the mixture (i.e. superposition) of multiple Gaussian distributions. Here rather than identifying clusters by “nearest” centroids, we fit a set of k gaussians to the data. And we estimate gaussian distribution parameters such as mean and Variance for each cluster and weight of a cluster. After learning the parameters for each data point we can calculate the probabilities of it belonging to each of the clusters.
Every distribution is multiplied by a weight ππ(π1+π2+π3=1π1+π2+π3=1) to account for the fact that we do not have an equal number of samples from each category. In other words, we might only have included 1000 people from the red cluster class and 100,000 people from the green cluster class.
![image](https://user-images.githubusercontent.com/33064867/209317908-60c172a4-291a-449b-8d65-e3007a559ea8.png)

Expectation Maximization
Expectation
The first step, known as the expectation step or EE step, consists of calculating the expectation of the component assignments CkCk for each data point xi∈Xxi∈X given the model parameters πkπk μkμk and σkσk.

Maximization
The second step is known as the maximization step or MM step, which consists of maximizing the expectations calculated in the E step with respect to the model parameters. This step consists of updating the values πkπk, μkμk and σkσk.

The entire iterative process repeats until the algorithm converges, giving a maximum likelihood estimate. Intuitively, the algorithm works because knowing the component assignment CkCk for each xixi makes solving for πkπk μkμk and σkσk easy, while knowing πkπk μkμk σkσk makes inferring p(Ck|xi)p(Ck|xi) easy. The expectation step corresponds to the latter case while the maximization step corresponds to the former. Thus, by alternating between which values are assumed fixed, or known, maximum likelihood estimates of the non-fixed values can be calculated in an efficient manner.

Algorithm
•	Initialize the mean μkμk, the covariance matrix ΣkΣk and the mixing coefficients πkπk by some random values(or other values).
•	Compute the CkCk values for all k.
•	Again Estimate all the parameters using the current \C_k values.
•	Compute log-likelihood function.
•	Put some convergence criterion
•	If the log-likelihood value converges to some value (or if all the parameters converge to some values) then stop, else return to Step 2.
This algorithm only guarantee that we land to a local optimal point, but it do not guarantee that this local optima is also the global one. And so, if the algorithm starts from different initialization points, in general it lands into different configurations.

3.	Agglomerative clustering
Also known as bottom-up approach or hierarchical agglomerative clustering (HAC). A structure that is more informative than the unstructured set of clusters returned by flat clustering. This clustering algorithm does not require us to prespecify the number of clusters. Bottom-up algorithms treat each data as a singleton cluster at the outset and then successively agglomerates pairs of clusters until all clusters have been merged into a single cluster that contains all data. 
given a dataset (d1, d2, d3, ....dN) of size N
-- compute the distance matrix
for i=1 to N:
   --as the distance matrix is symmetric about 
   --the primary diagonal so we compute only lower 
   --part of the primary diagonal 
   for j=1 to i:
      dis_mat[i][j] = distance[di, dj] 
each data point is a singleton cluster
repeat
   merge the two cluster having minimum distance
   update the distance matrix
until only a single cluster remains
![image](https://user-images.githubusercontent.com/33064867/209318305-48949062-c5d1-4b6d-a66a-2fd19d443e74.png)

# Conclusion:
1. EDA was used to examine the data.

2. Textual data were converted using stemming. Data cleansing for the textual data was done.

3. Textual data were transformed using TF-IDF.

4. Dimensionality was reduced by using PCA. The explained variance vs. components graph was used to choose the components.

5. Clustering using K-means was used.

6. Using the elbow curve graph and the Silhouette score, the ideal number of clusters was discovered.

7. The characteristics of several clusters were compared.

8. Utilizing a count vectorizer, a content-based recommendation system was developed. For any movie name entered, it suggests 10 other films or TV shows that are similar.








