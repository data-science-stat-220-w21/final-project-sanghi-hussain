# Today's Top Hits

## Website Link

Our website can be found [here]()

## Roadmap

### We downloaded the following data sets: 
- data.csv (saved as all_data): this is a consolodiated file which includes data from all the other 
  data sets
- data_by_artist.csv: information on the song metrics by artist
- data_by_genres: information on the song metrics for each genre in the data set
- data_by_year: averages the metrics for each song in all years
- data_w_genres: information on song metrics for each artist and genre

### We primarily used the data.csv and data_by_year files. 

Our analysis can be found in the following files:

- app.Rmd: This file has our code for the actual report. This is where all the content is. 
- Decision_Tree_Random_Forest.Rmd: This file has all the code for training and saving our Random Forest models.
- Data_Wrangling.Rmd: This file contains all the data wrangling we did for training our model. 


## Technical Report

### We used the following class tools/methods:

- We used the tidydata methods to transform data_by_year into a longer format so that there is a column for the metric and the associated value. This helped us plot the metrics over time and differentiate between them types (can be seen in app.Rmd)

- Since we had so many years in the data set we decided to categorize them into decades. We created a  function and applied that to all the years in the data set (Data_wrangling.Rmd).

- In order to collapse the popularity variable into smaller bins we used the `forcats` packages, specifically exploiting the `fct_collapse()` function (Data_wrangling.Rmd).

-  To make our predictions we used the random forest classification studied in Statistical Learning. Since we didn't have a binary predictor it made sense to use this classification.Random forests are a lot more robust than a simple decision tree as it aggregates many decision trees reducing overfitting (Decision_Tree_Random_Forest.Rmd).

- Random Forest Classification was used with 500 trees and the default mtry value which is the square root of the number of predictors (in this case it is the square-root of 6). Specifically, we use two prediction models - one with musical decade as the the main predictor and one with popularity. 

- In order to build the website and the interactive feature we used tools learned from Shiny. We used the slider bar as well as the check box features. Additionally, we used the HTML text features to display the results from the prediction model. 