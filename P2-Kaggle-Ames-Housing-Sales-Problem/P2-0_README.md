## Project 2. Ames Housing Data and Kaggle Challenge

### Problem statement:
This project seeks to optimise a regression model predict house sale prices in Ames, Iowa, based on the Ames housing dataset provided.
​
We will look primarily at the following models: Linear Regression, Lasso, and Ridge. How successful the model is is based on how close (_judged by a **RMSE score**_) the predicted sale prices are to the actual sale prices, which is a hidden value set on Kaggle.  
​
The information gathered from this study can act as a case study on some of the micro and macro factors that affect housing sale prices, giving some insight into the property market. Extrapolations from such a study into a local property microcosm can potentially give insights on other, comparable scenarios in other neighbourhoods and countries' housing markets, information valuable to consumers, investors, and academics alike.
​
### Data source:
Ames Housing price dataset from Truman State University.

### Methodology:
#### P2-1: Summary of Data
This notebook aims to summarise the EDA portion of the project, highlight necessary differences, and process any and all data cleaning before the actual analysis commences. We will be looking at the data through the following workflow:

1. **Summarise differences between train and test sets**, and any transformations that need to be taken into account when processing the train or test sets.
2. Looking into **missing data**, **classification considerations for features**, as well as **treatment for each field**. In this section, we will also look into qualitative reasons for including or excluding some fields, as well as how data will need to be treated before any regression analysis can commence.
3. [EDA] Look at **inter-correlation of existing data**. Generally, if features are highly correlated, including both would be counter-productive to the effectiveness of our prediction model. Conversely, some uncorrelated data could also be considered noise that would only confuse our model. These will also need to be removed.
4. Lastly, a brief look at the train set and Sales Price correlation.

#### P2-2: Regression Modeling
In this codebook, we will focus more on working through various logical and iterative steps to try and ascertain a good model for predicting the SalePrice of the Ames housing dataset.

Our general 'modus operandi' will be as follows:
1. Test the general model with all (relevant) features, and compare the usage of Ridge, Lasso, and vanilla linear regression.
2. From the first test, we will determine which of the 3 has the best performance (most likely Lasso).
3. We will test subsequent models with the best estimator strategy only to try and find the model with the best performance.
4. Once we have settled on something, we will test the other estimators again.

In this project, we will focus mostly on the impact specific variables have the accuracy of our model, and whether segments of the Ames dataset suggest that customers behave differently when certain conditions are met. This conjecture is based particularly on the economic concept of **market segmentation**, and how some groups of customers/buyers have different considerations and incentives to making a purchase, and thus have to be marketed to individually and differently.

### Project Directory:
<ul>
<li>P2-1: Summary of Data</li>
<li>P2-2: Regression Modelling</li>
</ul>
​
**Notebook P2-1** directory:
<ul>  
  <li>0 Summary - Aim of Notebook</li>
  <li>1 Dataset Summaries</li>
        <ul>
        <li>- 1.1 Feature Analysis between Train/Test sets</li>
        <li>- 1.2 Missing Data</li>
        <li>- 1.3 Feature Considerations and Feature Engineering</li>
        <li>- 1.4 Exporting out treated datasets</li>
        </ul>
  <li>2 EDA</li>
        <ul>
        <li>- 2.1 General Correlation Check with SalePrice</li>
        <li>- 2.2 Looking at highly correlated data</li>
        <li>- 2.3 Grouping data into related sets and looking at correlations</li>
        <li>- 2.4 Market Segmentation and Prediction Performance</li>
        </ul>
</ul>
​
**Notebook P2-2**:
<ul>
<li>3 Testing of Different Regression Permutations</li>
    <ul>
    <li>3.1 Regularisation with All Features, using Lasso and Ridge</li>
        <ul>
            <li>3.1.1 Linear Regression</li>
            <li>3.1.2 Lasso</li>
            <li>3.1.3 Ridge</li>
            <li>3.1.4 Conclusion</li>
            <li>3.1.5 Impact of removing fields with high nulls</li>
        </ul>
        <li>3.2 Regression with only features with >50 correlation with SalePrice</li>
        <ul>
            <li>3.2.1 Removing high null fields again from 3.2</li>
        </ul>
        <li>3.3 Looking into key features as metrics for segmentation</li>
        <ul>
            <li>3.3.1 Lot Shape</li>
            <li>3.3.2 Overall Quality</li>
            <li>3.3.3 Overall Quality, top 20 correlated features</li>
        </ul>
    </ul>
<li>4 Conclusions and Limitations</li>
<li>5 Improvements</li>
</ul>


### Conclusion:
The results from our optimisations seems to suggest that market segments do have differing wants, and thus segemented data react to various factors and variables differently. 

Segmented results do show promise in being good predictors, but more tuning is ultimately required in order to further tune the model's performance.

**Final (best) run:**  
LassoCV run on Overall Quality segmentation, run 6  
Kaggle RMSE score: 21,493


#### Limitations  
1. There was not enough time to do a full exploration of all the features within the dataset. With more tweaking, it is very likely that some of the features unexplored would have impacted the performance of the model to a larger degree.
2. I chose not to focus on too many things when trying to optimise and explore the effects of the variables on the overall model, such as noise and (direct) inter-correlation analysis. These things ultimately have an impact on the accuracy of the model, and clearing the noise would definitely improve the performance as well.

### Improvements:
Due to time constraints, a lot of optimisations were not implemented. The following can be improved on should there come a time to further optimise the resultant models.

1. Keep the naming of the models consistent and unique, allowing for the trained models to be called easily later on when needed.
2. Some of the algorithms and transformations can be streamlined into more general, universal functions, with a little standardisation and tweaking.
3. Use a cleaner naming convention for the runs and model variables, allowing for more powerful and generalised functions to be leveraged on.
4. Creating an algorithm to sift through variables, perhaps 1-by-1, and their significance to each subset, might yield a more optimal result in most cases. There is a good chance that the variance seen in the performance of each segment (e.g. OQ = 0,1, and 2) is in part due to alot of variables creating noise and obscuring proper accuracy.
5. Consider removing fields that may cause more noise than good for the model performance.
6. Hyperparameter tuning could also be used to further optimise the models to get the best results.