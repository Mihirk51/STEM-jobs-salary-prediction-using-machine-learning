# STEM-jobs-salary-prediction-using-machine-learning

Using a dataset I found on kaggle ( https://www.kaggle.com/jackogozaly/data-science-and-stem-salaries ) to predict the dependant variable. I used totalyearly compensation. However, any other variables could've been used as the independant variable.

I cleaned the dataset in excel to remove any empty records or records that contain na, NA, or N/A. The final dataset has been uploaded to the github repo for this project. I then selected the top 10 job positions or titles that contain the most records. Plotted the bar graph to visualize the average totalyearlycompensation for these positions.

Since we have one categorical column in the final dataset which is the title column, we need to encode this into numerical values for the machine learning algorithms. I could've used LabelEncoder which converts the categories into numbers starting from 0 and assigning the next number for every unique catergory. However, this creates the perception that catergory with a higher number is better than the category with the lower number, which is not the case. Therefore, I decided to use OnehotEncoder or using dummies, which basically converts each category into it's seperate column and the category has 1 or 0 depending on the record.

We then split the data into training set and testing set. Using 75% of the data for training. At this staage , the data is ready for fitting into the machine learning algorithm

Using linear regression first. We get absolute error as 24812 which is not bad considering the average totalyearlycompensation for the entire dataset. We then Use sequential feature selector from mlextend to find out the number of independant variables or features beyond which there is no gain in performance or accuracy on addinf more features. From the plot, this number is around 5 features.

Then, we use random forest to see if it performs any better. The mean absolute error here is 7712 which is far better than it was for linear regression. 

We can see that using the default settings for randomforest, we still get better scores than linear regression for this particular dataset. Therfore, implementing random forest for predicting salaries or totalyearly compensation is a better option. Similarly, we can predict other variables too such as bonus, stock grant value, or any of the other parameters