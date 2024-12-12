# CSE151A-Earthquake-ML-Project
**Group members**
1. Brandon Rogers 
2. Girma Terfa 
3. Kanishka Katragadda    
4. Sankalp Kumaraswamy<br><br>

**Links**

[Data Download Link](https://www.kaggle.com/datasets/antoniocola/earthquake-perception-dataset)

[Jupyter Notebook Link](https://colab.research.google.com/drive/18wviw9PHky41dNvtAJUs4lkZ43YkiXUk?usp=sharing)

**Introduction**
The issue of post-seismic stress is a unique and interesting topic that can bring light to issues faced by survivors of disasters around the world. We aim to analyze the data gathered from subjects living in the Campi Flegrei area in Italy which is subject to frequent earthquakes and build machine learning models to predict certain psychological impacts. Performing exploratory data analysis can provide insights into this issue and building predictive models can assist with providing assistance and intervention for those struggling psychologically following seismic activity. Projects like these represent contributions to the understanding of earthquake-induced stress and provide a foundation for further research on mitigating the impact on exposed populations. 

**Initial Preprocessing**

After looking through our data, several preprocessing steps will need to be taken before training can begin. As discussed in our notebook, there are a few features with a significant amount of missing values, particularly for political orientation and salary. We could replace these values with modal values or some other representative value if we are running predictions using these features so we do not have to drop the data. We also have several categorical variables in the dataset. These will need to be encoded during the preprocessing phase. The ones with no inherent order and few categories can be done with one-hot encoding like sex or marital status. The features that have an inherent order that needs to be captured can be encoded using ordinal encoding which goes for features like salary or house floor. Most of our numerical values are already on standardized scales akin to a rate from 1 to 5 scales, so we will not have to standardize those. There are also several true or false features that can easily be encoded with ones and zeros. 

**Milestone 3: Pre-Processing**

In Milestone 3, we conducted extensive preprocessing on our Earthquake dataset to prepare it for building a predictive model. Based on the correlation matrix created in Milestone 2, we identified numerical features that were weakly correlated with our target variables, fear and anxiety (correlation < 0.15). These features were dropped to reduce noise and improve model performance. Notably, since fear and anxiety were highly correlated, we chose fear as our primary target variable and excluded anxiety to avoid redundancy.

The dataset consisted predominantly of categorical features, which were converted into numerical data using One-Hot Encoding. This transformation created new binary columns for each category within a feature, assigning values of 0 or 1 based on the encoding. This step ensured that categorical data could be effectively utilized by our model.

Because our One-Hot Encoding lead to a lot of NaN columns, we opted to drop the NaN columns to further reduce noise and number of features.

Then, when had to deal with missing/null values within our dataset. We were considering either using mean/modal values to fill up the null data, or completely removing the rows with null data. We realized that since our features are binary, filling them up modal/mean values may not be the best approach. We also noticed that the null valued rows constituted a relatively small percentage of the total, so we decided on removing said rows from our dataset completely.

Next, we implemented a linear regression model, splitting the data into training (80%) and testing (20%) sets. The model was trained on the training set and evaluated on the testing set. Key metrics were calculated to assess performance, including the R-squared scores and the mean squared errors (MSE) for both training and testing predictions. These metrics provided insight into the model's accuracy and its ability to generalize to unseen data. Using these metrics we determined that our model was overfitting, and we picked out a couple other models we might like to use in the future.

**Milestone 4: Second Model**

In Milestone 4, we tried to improve upon our first model that used Linear Regression, by using Decision Tree Regressors for our second model. Decision trees allowed us to split on the data and capture more complex, potentially non-linear relationships. And since decision trees split data based on categories directly, the need for one-hot encoding was eliminated all together, greatly reducing the dimensionality of our data. Therefore, we re-processed our dataset by conducting Label Encoding on our categorical columns instead of the OneHotEncoding we used for Linear Regression, as this greatly reduced the number of columns, and made it easier to organize.

Then, when had to deal with missing/null values within our dataset. We were considering either using mean/modal values to fill up the null data, or completely removing the rows with null data. We realized that sex, age and family disabilities constituted a very small percentage of the total rows, we decided to remove them. For political_orientation and vehicle type, we replaced null cells with 'None', as that was one of the values, and for salary, we replaced it with the mode, as we discussed that that the mode would likely be representative of the general economic situation. 

Then, since max_depth is a key metric and argument in Decision Tree Regressor to determine the amount of pruning conducted, and the level of accuracy we will acheive, we decided to conducted simulations on max_depths from the range 1-20, and plotted a graph to determine the best hyperparameter value for us to use.

Next, we implemented the Decision Tree Model, splitting the data into training (80%) and testing (20%) sets. The model was trained on the training set and evaluated on the testing set. Key metrics were calculated to assess performance, including the R-squared scores and the mean squared errors (MSE) for both training and testing predictions. These metrics provided insight into the model's accuracy and its ability to generalize to unseen data. Using these metrics we determined our models position on the fitting graph. Finally, we drew a figure of the Decision Tree our model had constructed, and observed the splitting patterns, to perhaps improve upon in the future.

