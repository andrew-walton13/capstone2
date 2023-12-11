# Summary of business problem and project objective

For this project, our goal is to dive into Home Credit's dataset with the objective on understanding crucial features and identifying any necessary data cleaning processes. The problem that Home Credit has is that when it makes loans it does not know whether or not the people they lend to will pay them back. Additionally, they are trying to broaden financial inclusion for people with insufficient or non-existent credit histories. This means that they have less data than normal and it makes it even more difficult to know whether the loan will be repaid. If they can find a good model that predicts repayment or non-payment with high accuracy, it will greatly help the bank know to whom they should and should not lend to. For this project we are going to create a predictive model capable of predicting with a high accuracy rate if a customer will or will not repay a loan. We want our model to help the company achieve better financial results, e.g. higher revenue and less costs from defaults on loans.


# Your group's solution to the business problem

Our group's solution to this problem was to build a predictive model that can use the data available to predict whether or not a customer is likely to miss payments on their loan. We went through an extensive EDA process that inlcuded many insights and improvements made to the data, including but not limiting to recognizing the imblance in the target variable which required upsampling and downsampling to resolve, setting an NA threshold of 20% for each predictor (if the percentage of NAs in a predictor was greater than 20%, we excluded that predictor from our models) and imputing the mean or median into many predictors where the NA percentage was lower than 20%. 


```{r, warning=FALSE, message=FALSE}

# Check distribution of target variable in train and test
prop.table(table(app_train$TARGET))
prop.table(table(app_test$TARGET))

```


        No        Yes 
0.91926935 0.08073065 

        No        Yes 
0.91927546 0.08072454


![image](https://github.com/andrew-walton13/capstone2/assets/123606002/baf6dfa4-5da8-4d3a-8ef2-f6208499c646)


We built various models in our group, as we wanted to try a few different options. We had three models that were pretty successful in various ways, but ultimately we decided that our logistic regression model would be the best model to recommend to home credit. There were various reasons behind this. One, it had a very good AUC score. Two, being a logistic regression model it was easier to explain why the model made the predictions that it made, which we wouldn't be able to do with the black box models we built. This is important for a financial institution to ensure there is reasoning behind loan decisions and could protect them from potential claims of discrimination. Third, it had the fastest compute time of all of our models by a fairly significant margin.


# Your contribution to the project

My contribution to the project consisted of a few different things. I built Naive Bayes and logistic regression models to help us predict whether or not customers would pay back their loans on time. I also put together our group notebooks in a way that merged our four notebooks into one fluid, cohesive, and structurally consistent notebook and put together the slide format for our slides and put them into a consistant format inline with the format suggestions from our professors. Additionally, I participated in the presenation of our work to our class.

# The business value of the solution

Our solution can be vey valuable to the company. If they were to use our model, they would be able to identify more of the people that are likely to default on loans and by avoiding lending to those individuals, they will save themselves millions of dollars in the process. It could also give them more confidence about lending money to more people, as a classification of 'non-default' could lead them to feel more confident in lending to that person and therefore provide more people with loans. This would be a great outcome since lending to people who are underserved by the wider banking system is a goal of the company. 


![image](https://github.com/andrew-walton13/capstone2/assets/123606002/ef146d44-8903-44ec-ab11-b9dd688f731c)


Assumptions in $100k
Average Cost of Default Loan -$10
Average Revenue from Non-Default Loan $1


![image](https://github.com/andrew-walton13/capstone2/assets/123606002/88f89a70-6aa0-4004-a86f-f25f134e6a76)


# Difficulties that your group encountered along the way

We encountered many difficulties along the way that had to be addressed. One example was the imbalance in the target variable. It was not immediately clear how we would address it, but we knew it needed to be addressed. We had to try many things such as upsampling, downsampling, and both, until we found that upsampling was ultimately the best choice for our model. We also had a lot of data with NAs, so setting a threshold and imputing the median helped us a lot with our NA problem. Another difficulty that we encountered was a long run time for many of our models, which ultimately lead us to pick the logistic regression model which had the second best results in terms of ROC-AUC but with a short compute time and more insight into the model we felt it was worth prioritizing that model.

# What you learned in the project

I learned a lot from this project, including the importance of trying many different model types and seeing the different results that we could come up with. In this case, we were working with an extremely large data set and a target variable with heavy imbalance. This meant that many of the initial models I tried that were more simple always predict the majority class. The EDA process was extensive due to the size of the data, but it is important to get that right if you want to have a successful model. Many times I have worked with much simplier data sets, but in this case I learned the importance of really digging deep and doing a lot of work during the EDA phase. 
