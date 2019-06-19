# Supervised-SemiSupervised-and-Unsupervised-Learning
Using the Breast Cancer Wisconsin (Diagnostic) Data Set. 
<br>
Dataset description : There are IDs, classes (Benign=B, Malignant=M), and 30 attributes. This data has two output classes.
<br>

MONTE-CARLO SIMULATION : M = 30 times. <br>
<br>
SUPERVISED LEARNING : Train an L1-penalized SVM to classify the data. We use 5 fold cross validation to choose the penalty parameter normalized data. <br>
<br>
SEMI-SUPERVISED LEARNING/ SELF-TRAINING : select 50% of the positive class along with 50% of the negative class in the training set as labeled data and the rest as unlabelled data. <br>
STEPS --->
<br>
1) We train an L1-penalized SVM to classify the labeled data using normalized data. Choose the penalty parameter using 5 fold cross validation.
<br>
2)Find the unlabeled data point that is the farthest to the decision boundary of the SVM. Let the SVM label it (ignore its true label), and add it to
the labeled data, and retrain the SVM. Continue this process until all unlabeled data are used. <br>
<br>
UNSUPERVISED LEARNING : Run k-means algorithm on the whole training set. Ignore the labels of the data, and assume k = 2.
STEPS ---> <br>
1) The k-means algorithm is run multiple times, and initialized randomly.
<br>
2) Compute the centers of the two clusters and find the closest 30 data points to each center. 
Read the true labels of those 30 data points andtake a majority poll within them. The majority poll becomes the label
predicted by k-means for the members of each cluster. 
Then compare the labels provided by k-means with the true labels of the training data and report the average accuracy.
<br>
3) Classify test data based on their proximity to the centers of the clusters. <br>
<br>
For all the above algorithms, average accuracy, precision, recall, F-score, and AUC over M runs, and ROC and the confusion matrix is computed.
<br>
Conclusions are reported.
