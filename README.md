# CSE151A-Earthquake-ML-Project
**Group members**
1. Brandon Rogers 
2. Girma Terfa 
3. Kanishka Katragadda    
4. Sankalp Kumaraswamy<br><br>

**Links**

[Data Download Link](https://www.kaggle.com/datasets/antoniocola/earthquake-perception-dataset)

[Jupyter Notebook Link](https://colab.research.google.com/drive/18wviw9PHky41dNvtAJUs4lkZ43YkiXUk?usp=sharing)

**Initial Preprocessing**

After looking through our data, several preprocessing steps will need to be taken before training can begin. As discussed in our notebook, there are a few features with a significant amount of missing values, particularly for political orientation and salary. We could replace these values with modal values or some other representative value if we are running predictions using these features so we do not have to drop the data. We also have several categorical variables in the dataset. These will need to be encoded during the preprocessing phase. The ones with no inherent order and few categories can be done with one-hot encoding like sex or marital status. The features that have an inherent order that needs to be captured can be encoded using ordinal encoding which goes for features like salary or house floor. Most of our numerical values are already on standardized scales akin to a rate from 1 to 5 scales, so we will not have to standardize those. There are also several true or false features that can easily be encoded with ones and zeros. 

**Milestone 3: Pre-Processing**
In Milestone 3, we conducted extensive preprocessing on our Earthquake dataset to prepare it for building a predictive model. Based on the correlation matrix created in Milestone 2, we identified numerical features that were weakly correlated with our target variables, fear and anxiety (correlation < 0.15). These features were dropped to reduce noise and improve model performance. Notably, since fear and anxiety were highly correlated, we chose fear as our primary target variable and excluded anxiety to avoid redundancy.

The dataset consisted predominantly of categorical features, which were converted into numerical data using One-Hot Encoding. This transformation created new binary columns for each category within a feature, assigning values of 0 or 1 based on the encoding. This step ensured that categorical data could be effectively utilized by our model.

Because our One-Hot Encoding lead to a lot of NAN columns, we opted to drop the NAN columns to further reduce noise and number of features.

Then, when had to deal with missing/null values within our dataset. We were considering either using mean/modal values to fill up the null data, or completely removing the rows with null data. We realized that since our features are binary, filling them up modal/mean values may not be the best approach. We also noticed that the null valued rows constituted a relatively small percentage of the total, so we decided on removing said rows from our dataset completely.

Next, we implemented a linear regression model, splitting the data into training (80%) and testing (20%) sets. The model was trained on the training set and evaluated on the testing set. Key metrics were calculated to assess performance, including the R-squared scores and the mean squared errors (MSE) for both training and testing predictions. These metrics provided insight into the model's accuracy and its ability to generalize to unseen data. Using these metrics we determined that our model was overfitting, and we picked out a couple other models we might like to use in the future.

