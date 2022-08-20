# misogynist-text-detection
Identifying misogynistic and non-misogynistic text

### Project Scenario
Misogyny means "dislike of, contempt for, or ingrained prejudice against women.", i.e. any definitions that disparage women.
In this project, we will use an annotated dataset to build a machine learning model to classify text for misogyny.

### What we'll be doing:
1. Download Urban Dictionary text corpus and clean the data up (Part I)
2. Perform wordcloud analysis (Part II)
3. Transform the data for feature extraction and apply machine learning techniques to train a model to predict whether a text string is misogynistic  (Part III)

### Dataset
The dataset that we will work with comes from the hard work of Theodore Lynn and her team, who manually annotated Urban Dictionary definitions. More information can be found in a research publication <a href='https://www.sciencedirect.com/science/article/pii/S2352340919305773'>here</a>.

# Part I - Data Preparation
In the notebook `Misogynist Text Detection Part I - Data Preparation`, we first import the csv using pandas to view our data in a tabular format. We then conduct an initial cleaning to investigate and fill NaNs, giving us a DataFrame of 2286 x 2 as below:

![image](https://user-images.githubusercontent.com/101868958/185730329-b581670d-1093-49be-867d-6bf1dd022289.png)

Following that, we clean the data further by removing any sort of punctuation from the definitions, as well as lowercasing all definitions. This resulted in a DataFrame as below:

![image](https://user-images.githubusercontent.com/101868958/185730395-2a24d447-ae14-4df0-a4e6-0c75cf61ef4e.png)

# Part II - Worldcloud
In the notebook `Misogynist Text Detection Part II - Wordcloud`, we performed wordcloud visualisations in order to get a sense of the most frequently occurring words among the text. In producing the wordclouds, the initial DataFrame was further grouped into DataFrames that were misogynist or non_misogynist by introducing the column 'is_misogyny' where '1' indicates misogyny and '0' indicates no misogyny.

A wordcloud containing both misogynist and non-misogynist text looks like:

![image](https://user-images.githubusercontent.com/101868958/185731176-92802c9a-ad8f-4a4d-b717-c11969ffb724.png)

A wordcloud of misogynist text looks like:

![image](https://user-images.githubusercontent.com/101868958/185731197-33ae3589-88b9-4618-a78e-c83a0212e2c9.png)

Comparing the wordclouds for misogynist and combined wordclouds it is evident that female and sexual references account for a majority of word appearances, even when the wordcloud includes non-misogynistic text.

This suggests that much of the discourse around Urban Dictionary revolve around femininity and sex, albeit not always in a positive manner.

# Part III - Model Training
In the notebook `Misogynist Text Detection Part III - Model Training`, prior to training our models, we used `STOPWORDS` from the `wordcloud` library to engineer a `cleaned_definition_nostop` column that contained our definitions without stopwords.

Using `sklearn`'s ML libraries, we trained 3 models: Logistic Regression, Decision Tree Classifier and Random Forest Classifier.

Evaluating the F1 Scores for each model, we found that the models generally performed well with the lowest scoring being the Logistic Regression model with an F1 Score of 0.770.

![image](https://user-images.githubusercontent.com/101868958/185731399-7345822e-bd70-466e-bb96-9e46fe527572.png)

We decided to use the Random Forest Classifier as our model for prediction as it provided the best performance. Tweaking the TfidfVectorizer, we found that the model provided the best performance when max_features was set at 850.

![image](https://user-images.githubusercontent.com/101868958/185731668-f2a66654-b83a-43b6-a762-e66f1977ff0f.png)




