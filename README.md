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
In the notebook `Misogynist Text Detection Part II - Wordcloud`, we performed wordcloud visualisations in order to get a sense of the most frequently occurring words among the text.
