# CSE151A-Earthquake-ML-Project
**Group members**
1. Brandon Rogers 
2. Girma Terfa 
3. Kanishka Katragadda    
4. Sankalp Kumaraswamy<br><br>

**Data Download Link**

[Earthquake Dataset Kaggle](https://www.kaggle.com/datasets/antoniocola/earthquake-perception-dataset)

**Initial Preprocessing**

After looking through our data, several preprocessing steps will need to be taken before training can begin. As discussed in our notebook, there are a few features with a significant amount of missing values, particularly for political orientation and salary. We could replace these values with modal values or some other representative value if we are running predictions using these features so we do not have to drop the data. We also have several categorical variables in the dataset. These will need to be encoded during the preprocessing phase. The ones with no inherent order and few categories can be done with one-hot encoding like sex or marital status. The features that have an inherent order that needs to be captured can be encoded using ordinal encoding which goes for features like salary or house floor. Most of our numerical values are already on standardized scales akin to a rate from 1 to 5 scales, so we will not have to standardize those. There are also several true or false features that can easily be encoded with ones and zeros. 
