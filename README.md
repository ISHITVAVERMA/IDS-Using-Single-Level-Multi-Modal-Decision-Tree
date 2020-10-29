# Instrusion_Detection_System_Using_Multi_model_decision_Tree
Basic Machine Learning Code

This project can be run using Google collab Environment or juyptier notebook

We already know that network intrusion systems require bulk amounts of raw data to be dealt with. The most crucial building block of developing such a sophisticated system is Feature Selection. One thing which has a major effect on the dimensionality of the dataset is the complexity of the model. It results in obtaining high computational time and costs and also low classification accuracies. A significant number of techniques and approaches are used to get rid of repetitive and insignificant features.
These methods are chosen in such a way that we select only those features which are optimal and can be used to enhance the performance of the model. The 2 basic methods used for feature selection are: wrapper methods and filter methods.
Wrapper algorithms - In these types of algorithms a learning algorithm is used to make a decision for the features. In the
Filter algorithms - In these types of algorithms a measure which is not dependent on the others is employed. Some of the measures are consistency, information and distance. A relationship between the set of features can be estimated using these measures.
We will be using Information Gain (IG) to select the subset of relevant features in this project. Information Gain often costs less and is faster as compared to the wrapper methods. We calculate Information gain for all the attributes present in the training dataset. It is calculated for each class separately. In the next step the values of the information gain are ranked i.e. the feature with the highest information gain being at rank 1. It means that this particular feature can distinctively classify for the particular class. If the value of the Information gain is less than the fixed threshold value for a particular feature, that feature can be eliminated from the feature space. A better and optimal threshold value is obtained by examining the distribution of Information Gain for each attribute tested with different values of fixed threshold on the training dataset.
In the next stage the feature selection for each category can be broken down into 4 stages:
Stage 1: We divide the training dataset into 4 datasets. The training dataset is divided into 4 datasets in such a way that each dataset consists of records belonging to the same attack class along with some of the records of the original dataset. This stage is performed so that the feature selection method is unbiased while selecting features for frequently occurring attacks in the dataset. This step helps us in preventing unwanted bias and to make sure the results retrieved are accurate.
Stage 2: In this stage the datasets for each attack class are sent separately as input into the method used to calculate the information gain. The output of this method gives us the most significant features for each attack type.
Stage 3: In the third stage we generate a list of ranked features for each attack class. Now we eliminate all the irrelevant features from the list in accordance with the fixed threshold values.
3.1.2 Combining Optimal Features:
In the last stage of feature selection, we combine the list of features generated for each attack into a single list . For some of the attack classes the highest ranks
i.e. the top 4 features chosen for classification. But for some types of attack classes we can only take 1 feature since that particular feature is at the top of the rank table and the remaining features are at the very bottom of the table. So, the final set of combined optimal features can be used to entirely distinguish the attack types.
3.1.3 Building a Classifier:
The obtained subset of relevant features of each attack type in the above step is now used to build a classifier in this phase. As the model that is going to be used is a decision tree classifier, the dataset containing only the obtained subset of features is used to build 4
classifiers i.e. 1 for each attack type. This creates trees with only the relevant features of each attack type in each decision tree.
3.1.4 Model Used: Decision Tree Classifier:
A Decision tree is an algorithm which takes decisions at each node of the tree and is widely used for regression and classification. It is a supervised learning algorithm in Machine learning where which attribute should be at which node is learnt by using a set of labelled examples. The main advantage in using decision trees is that they can be trained very easily and they can even classify non linear data. It is more productive than most of the classification algorithms in ML like K-Nearest Neighbours in most of the cases. The common measures used to select attributes at each node in Decision trees are Info gain and Gain ratio.[13]
Entropy: A measure of impurity which is defined as the degree or the amount of uncertainty in the randomness of elements
E(S) = Σ−=12 Homogeneity of a sample is calculated by the Entropy.
● Entropy = 0, if the sample is absolutely homogeneous
● Entropy = 1, if the sample is uniformly divided.
Information Gain: The relative variation in entropy can be measured using Information Gain which corresponds to an independent attribute. While constructing a Decision tree, an attribute at a node is selected by calculating the information gain of all attributes and determining the attribute which has the maximum information gain. Info gain calculates the information encompassed by each feature.
Gain (D, Attr.) = Entropy(D) – Entropy (D, Attr.)
Where Gain (D, Attr.) is the information gain of the attribute Attr. Entropy(D) is the entropy of the complete set, and after implementing the attributes entropy is calculated using Entropy(D, Attr). Overfitting is one of the main problems of the decision tree as it constructs its nodes by thoroughly going through the entire training set which may result in a low accuracy while using unknown data like the test set.
Decision Tree works in the following way:
a. The best attribute is identified for separating the records using the Attribute Selection Steps (ASM).
b. Now the dataset is split into smaller subsets by using the previously selected attribute as the decision node.
c. A tree is built by the algorithm by iteratively executing this cycle before any one condition fits in :
1. There are no attributes left over anymore
2. No more instances do exist
3. The Tuples generated have the same value of the attribute .
