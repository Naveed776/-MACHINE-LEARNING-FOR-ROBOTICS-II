# -MACHINE-LEARNING-FOR-ROBOTICS-II
# CONTENT

In that presentation were going to cover different points:
first of all discussed the problem statment and then i can brifely
discussed a data set
Second some pre-pocessing then describe about model 
training then evaluatio of model and at least features and conculsion

# Problem statemnt
 
The most common reason include security issue, hotel mangemnt, health purpose might also
intersted is to knowing when a room is been loceked or isloted 
other reason of doemstic applancies.
used in robotics for environment mapping and localization. 
The algorithm is used to build a map of an indoor environment 

# Data set

our data is depend on 5 features light ,temearures humidity co2 Our target variable was 
the occupancy of the room where 0 corresponds to the empty room and 1 to the occupied room.
The dataset has 2665 rows, and 0 Null parameters, All values are Real numbers

# PRE-PROCESSING

our traget is when the room is occupied or empty, its time to process our data set to make it
useful. The first thing we’ve to do is check correlations between variables,
keeping in mind that Room occupancy is the actual target. 
We use two techniques to find it. First, 
we use pandas.corr() method and map the results on a heatmap to 
find the highest correlation value with occupancy. 
Secondly, we overlapped the data of each feature individually on a distribution plot,
when the room is empty or occupied. So that, we have a better visualization of the relation.
By comparing each feature plot, We noticed that light is the most correlated variable,
while Humidity is the second most. 

# Detection and removal outliers 

The second step is detecting and removing outliers: 
The best way to identify the outliers in the box plot. 
It will find the minimum, lower quartile (25th percentile), 
median (50th percentile), upper quartile (75th percentile), 
and maximum of a continuous variable. 
There are only 3 outliers from the light sensor feature

Now, we are applying normalization to our dataset,
which transforms feature value into 0-1. 
Because, we assume that few algorithms (that we used)
expect the normalized data input, to avoid biased results. 
For example SVM and logistic regression.

# Basic Model Training!
Now data is ready to train,  so we start with basic model training. 
Here we train different models and present their confusion matrices to understand the performance. 
We select the params by manual tuning, to avoid complexity at this point. 
We started with a decision tree, with a max depth of 4, then Random Forest with the same depth and no of the estimator is  2500.
Then K-Neighbors with 7 no of neighbors. Then, Support vector classifier and Logistic regression. 
In both, we used a data normalized and non-normalized data.We can see that the decision tree has the highest metrics values (Accuracy score and F1), Also there is no difference in results of SVC and Logistic regression with and without the normalized dataset. It's time to work further with decision tree.As we saw, the Decision Tree is performing well. But we can still find the best parameters to get better results

# Conclusion


As we try to follow the Machine Learning life cycle in the project. We realized that the Decision Tree is the most accurate model, and we got a perfect accuracy. Also, we try Percentile and IQR-based filtering and notice that IQR is the best fit in our case. Through the analysis of feature importance, we can assume that Light is the most important feature of the classification. In the End there are some effects which does not create difference, which is the normalization of the data.


