# Classifying Student Performance using Machine Learning

## Introduction
Predicting student performance based on qualitative and quantitative data can be quite challenging with machine learning, especially with qualitative data [6]. An example of qualitative data is the answer to this question: “On a scale from 1-3, 1 being ‘never,’ and 3 being ‘always,’ how often do you read a book?” The answer to this question can be inconsistent because each student can have their own definition of “always” or “never” in terms of the frequency they read a book. Quantitative data such as the answer to: “Exactly how many hours do you read per week?”, can be much more accurate because the scale between each student asked is now consistent. This helps a machine learning model to learn and generalize the dataset better when data is much more consistent. How a dataset is structured is very important [4] and there currently is not an established and effective framework that can be used when collecting data about students to be used in performance classification. However, we cannot always subject every dataset to be perfectly created. This paper explores the Higher Education Students Performance Evaluation Dataset [10] and takes a small glimpse of the most and least important factors that affect student performance. The goal of this paper is to find some of the best machine learning techniques to classify student performance with high accuracy.

## Related Work
Yilmaz and Sekeroglu [1] experimented with a Backpropagation Neural Network, Radial-Basis Function Neural Network, Decision Tree Classifier, and Logistic Regression to perform the classification of student performance. They found that the Radial-Basis Function Neural Network performed the best, achieving the highest accuracy rates from 70% to 88%. The Backpropagation Neural Network was found to produce unstable results due to minimum attributes. The simpler machine learning models, Decision Tree Classifier and Logistic Regression did not perform well because of the complexity and non-linearity of data.

Gopi [3] used a Random Forest, Support Vector Classifier, Gaussian Naive Bayes, K-Means, and K-Nearest Neighbors to perform the classification of student performance. Although no results were presented in her paper, these machine learning models are effective for multi-class classification [2]. When classifying student performance, the letter grade of a student’s grade-point average tends to be the usual classification. Therefore, the classification of student performance is usually multi-class.

Li and Liu [5] used Long Short-Term Memory and their own Deep Neural Network to compare against the baseline of Linear Regression when evaluating student performance. Although their results concluded that Linear Regression performed the best by a very small margin, their own Deep Neural Network only performed worse by 0.1%. Long Short-Term Memory on the other hand performed worse than both models by 1%. All models achieved an accuracy of 63%-64% on the test set.

## Methods
Using the Higher Education Students Performance Evaluation Dataset [10], the data was split into 75% training and 25% testing. Then feature selection was performed using a Decision Tree.

![Feature Importances Graph](feature_importances.png)

The features with 0% importance (midtermExamPrepWhen, hasPartner, transportationToUniversity, graduatedHighSchoolType, sex) were dropped from the training and test sets.

Three machine learning techniques were used: K-Nearest Neighbors, Random Forest, and a Neural Network. All three models were optimized to score the highest accuracy on the test set. The K-Nearest Neighbors model used 3 as the number of neighbors and the “Ball Tree” algorithm [8]. The Random Forest model used 300 trees in the forest [7]. The Neural Network’s hidden layer used three dense layers, all with RelU activation functions. The first layer in the hidden layer has 100 nodes, the second with 50 nodes, and the third with 100 nodes. The output layer uses a Softnax activation function. The Neural Network uses Sparse Categorical Cross Entropy as the loss function, Stochastic Gradient Descent as the optimizer, and 100 epochs [9].

## Results
Based on the performances of the three machine learning techniques used on the test set, K-Nearest Neighbors performed the best with an accuracy of 38%. Next is Random Forest with an accuracy of 32% and last is the Neural Network with an accuracy of 22%.

| ML Model          | Test Accuracy     |
| ----------------- | ----------------- |
| KNN               | 37.84%            |
| Random Forest     | 32.43%            |
| Neural Network    | 21.62%            |

## Discussion
The overall performance of K-Nearest Neighbors, Random Forest, and a Neural Network suggest the models are overfitting the data, which can be alleviated with more data to train on. The simplest machine learning model, K-Nearest Neighbors performed the best. The results may also suggest the data is very complex and requires deep learning models to achieve a high test accuracy. With a much more optimized Neural Network, it may have been possible to get good accuracy. Despite these shortcomings, there is still a lot to take away from this dataset when performing feature selection. The feature selection using a Decision Tree described the least and most important factors of earning high grades as a student. The feature selection found that the following features have no impact on the grade they earned: when a student prepares for midterm exams (1: closest date to the exam, 2: regularly during the semester, 3: never), if they have a partner, how they transport to the university (1: bus, 2: private car/taxi, 3: bicycle, 4: other), the type of high school they graduated from (1: private, 2: state, 3: other), and their sex [10]. On the other hand, the course they were taking and their last semester’s cumulative grade-point average were the most important predictors of a student’s grade.

## References
1. Aliev, R. A., Kacprzyk, J., Pedrycz, W., Jamshidi, M., Babanli, M. B., & Sadikoglu, F. M. (2019). Student Performance Classification Using Artificial Intelligence Techniques. In 10th International Conference on Theory and Application of Soft Computing, Computing with Words and Perceptions - ICSCCW-2019 (Vol. 1095, pp. 596–603). Springer International Publishing AG. https://doi.org/10.1007/978-3-030-35249-3_76
2. Dataman, C. K. (2023, January 30). A wide variety of models for multi-class classifications. Medium. https://medium.com/dataman-in-ai/a-wide-choice-for-modeling-multi-class-classifications-d97073ff4ec8
3. Gopi Krishna, G. (2023, April 10). Higher Education Students Performance Evaluation Dataset Using Machine Learning. https://www.researchgate.net/publication/369917389_Higher_Education_Students_Performance_Evaluation_Dataset_Using_Machine_Learning
3. Khan, R. (2022, November 17). Importance of Datasets in Machine Learning and AI Research. DataToBiz. 
https://www.datatobiz.com/blog/datasets-in-machine-learning/
4. Li, S., & Liu, T. (2021). Performance Prediction for Higher Education Students Using Deep Learning. Complexity (New York, N.Y.), 2021, 1–10. https://doi.org/10.1155/2021/9958203
5. Pickell, D. (2023, May 3). Qualitative vs. Quantitative Data: What’s the Difference?. G2. https://www.g2.com/articles/qualitative-vs-quantitative-data
6. Sklearn.ensemble.randomforestclassifier. Scikit. (n.d.-a). https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html
7. Sklearn.neighbors.kneighborsclassifier. Scikit. (n.d.-b). https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html
8. Team, K. (n.d.). Keras Documentation: Keras API Reference. Keras. https://keras.io/api/
9. Yilmaz, N., & Sekeroglu, B. (2021, January 30). Higher Education Students Performance Evaluation Dataset Data Set. UCI Machine Learning Repository: Higher Education Students Performance Evaluation Dataset Data set. https://archive.ics.uci.edu/ml/datasets/Higher+Education+Students+Performance+Evaluation+Dataset 
