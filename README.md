# Titanic: Machine Learning from a disaster.

This is my interpretation of this kaggle competition: https://www.kaggle.com/competitions/titanic/overview.

I follow this workflow: 
1. Importing data and libraries. 
2. Performing a basic EDA over the dataset.
3. Filling missing data and encoding categorical variables. 
5. Splitting the data into train and validation sets.
6. Trained different classification model to choose the better.
7. Tuning and make predictions.

Summarize steps: 
## EDA (Exploratory Data Analysis)
Following my intuition I confronted various features with the target.

![download](https://user-images.githubusercontent.com/109316190/193087319-50fdbba2-acbb-4737-80e9-2a279ae88ef7.png)

Here I confronted the price paid for a ticket and tha age of the passenger: as shown by this plot, passanger that paid higer fares for boarding are also more like to survive.

I checked also the distribution of the survivers in respect to the class they boarded: 

![download](https://user-images.githubusercontent.com/109316190/193088214-57753a37-6c7e-4ca3-8f49-23617ce49876.png)

Here is shown that passengers from the first class was survived more than the other two.


## Modeling

To preprocess my data I decided to encode the categorical variable using `category` data type provided by pandas and using the code for every value. 

I decided to fill my data adding a bit more of information: I added columns to check if a value was missing. 

After preprocessing my data I decided to train 4 different models from `Scikit-Learn`, on my train set and evaluating them on my validation set.

The model I choose were:
* `LogisticRegression`
* `DecisionTree`
* `RandomForestClassifier`
* `KNeighbours`

I confronted the score of theese in the following plot: 

![download](https://user-images.githubusercontent.com/109316190/193090724-88f4bd0c-a32e-455f-86f2-decfac09c266.png)

and picked `RandomForestClassifier` to do the job, because of its higher base-line score.

After that I used `RandmoizedSearchCV` with a pipeline, to standarize the data, and tuned my model but unfotunately didn't see any improvement.

## Where to go from here? 

I think that obtain a better understening of the data could be beneficial. If possible I would also try to find new data to add more informations. 
I don't think that overtunning the model could be a good idea, but maybe I could try another model or preprocess the data in a more efficent way. 

