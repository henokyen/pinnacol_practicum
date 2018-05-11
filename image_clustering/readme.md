#Content based image clustering:
##I tried two ways to do this: 
###Method 1:
1. Run all images through the pre-trained model to get features. That is run feature_extraction.ipynb
2. Then do k-means clustering on the extracted features
3. This method in implemented in image_clutering.ipynb notebook

###Method 2:
A  little bit complex
1. Take an image and slice it into patches. Do that for all images in the dataset
2. For each patch from each image compute its color histogram
3. Use K-means to cluster the patches from every image
4. The resulting cluster labels represent a group of similar-looking patches (across all images in the data set)
5. Now, represent each image by cluster membership of its patches. E.g image_1 can be presented by {cl1, cl1, cl10, cl17, cl15}, where clx is a cluster label. That is each image is repressed by the clusters that its patches belong to
6. Use k-mode to do more clustering. This time to cluster original images based on common cluster memberships. K-mode is similar to k-means but it works for categorical values. The resulting clusters represent similar-looking images
7  This approach is implemented at image_clustering_2.ipynb

