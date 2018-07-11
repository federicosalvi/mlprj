# Federico Salvi 
# Machine Learning Project

## How to run the code

No particular dependency is needed, other than the usual numpy, matplotlib, sklearn and scipy. Pandas is used just to display the data nicely but it's not really necessary.

Since the data wasn't available in a convenient way but was scattered across many json files in many folders, I have included the pickle files for the data, the labels, and the names of the features (*props.npy*).

The first part of the notebook explains the steps that compose the algorithm I implemented, while the second part loads the data and tries to cluster it using various parameters, then I also try the spectral clustering algorithm provided with sklearn to check the results. 

Since the dataset I used doesn't seem to be very meaningful, I also tried with a toy dataset made of 4 nested circles.

## Algorithm parameters
spectral_clustering(x, sim='gaussian', sim_param=25, graph='mknn', graph_param=20, method='ng_jordan_weiss', k=5, plot=False)

- x is the data, which must be a numpy array of dimension (n_samples, n_features).
- sim is the similarity measure to use, can be either based on euclidean distance or just plain gaussian similarity.
- sim_param is the parameter to use in the similarity measure.
- graph is the type of graph to use, in order to enanche the locality of the neighborhood of the nodes. Can be one of 'eps', 'knn', 'mknn', 'full'.
- graph_param is the parameter to use as threshold in the selection of the closest neighbors. It is the value of epsilon in 'eps', or the number of neighbors in 'knn' and 'mknn'. It's ignore in 'full'.
- method is the type of spectral clustering algorithm to perform. Can be one of 'unnorm', 'shi_malik', 'ng_jordan_weiss'.
- k is the number of clusters to try to detect.
- plot determines whether or not to plot the intermediate results, like the similarity matrix or the eigenvectors of the laplacian.