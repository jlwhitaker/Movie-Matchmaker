# Movie Matchmaker

## Purpose 
Our goal was to create an application that would:
- → take user inputs regarding movies they have seen and enjoyed… 
- → provide recommendations based on a machine learning model for other movies to watch next

## Data Sources
**Analysing Gender Bias in Narrative Tropes:** github.com/dhruvilgala/tvtropes

- "_Analyzing Gender Bias within Narrative Tropes_": aclanthology.org/2020.nlpcss-1.23/
- Video/Slidedeck from the above GitHub: slideslive.com/38940608/analyzing-gender-bias-within-narrative-tropes
- The dataset can be found here: https://drive.google.com/file/d/1Duyz5ATlLHzwMidj15bWVnWHpdE4aRXn/view. 

This article was the inspiration for the project and provided much of the data that we initially used. 
The dataset that we started with was "_film_imdb_match.csv_", which contained 2,733,577 data points - more than enough data for us to use. 

## Data Cleaning and Preprocessing
To clean our data to use in our model, we performed the following:
- Reduced the data to include only tropes with over 16 movie mentions
- Removed columns that included data points not necessary for our desired outcome 
  - Columns removed: _Example_, _CleanTitle_, _tconst_, _trope_id_, and _title_id_
  - Remaining columns include: _Trope_ and _Title_
- Removed trailing and leading spaces from our dataset and reran the function to remove duplicates. 

We then took a random sample of 2000 films included in the dataset and created a new dataframe separating the data for the sampled films.
From there we set the _Trope_ column as our index and ran get_dummies to convert our categorical variables into dummy numeric data. 

## Creating the Model 
To create our model, we first ran PCA and t-SNE methods to reduce the number of features, and then clustered the data using KMeans.
The resulting model clustered the data into 7 groups. 

## Providing Movie Recommendations 
In order to provide recommendations, the clusters were first appended into separate dictionaries.
We removed duplicate title inputs from within each dictionary, then added each cluster list to a master _list_of_lists_ dictionary.
Finally, a for loop was created to run through each cluster list to search for a user-selected movie title, and output a random sample of 10 movie titles from the same cluster.



