# Movie-Matchmaker
Purpose - 
Create an application that would:
→ take user inputs regarding movies they have seen and enjoyed… 
→ provide recommendations based on a machine learning model for other movies to watch next

Data Sources - 
Analysing Gender Bias in Narrative Tropes (github.com/dhruvilgala/tvtropes)
This was the inspiration for the project and held a lot of the data that we initially used. 
Analyzing Gender Bias within Narrative Tropes: (aclanthology.org/2020.nlpcss-1.23/)
Video/Slidedeck from the above GitHub: slideslive.com/38940608/analyzing-gender-bias-within-narrative-tropes 
The dataset that we started with was film_imdb_match.csv and this held 2,733,577 data points.
This dataset held much more data than what we actually needed. 

Data Cleaning and Preprocessing - 
We removed tropes not included in at least 16 movies. 
We removed columns that included data points not necessary for our desired outcome. 
- Columns removed include: Example, CleanTitle, tconst, trope_id, and title_id.
- Remaining columns include: Trope and Title.
We then removed duplicates from our dataframe sample of 500.
- After completing this step, we noticed duplicates in our dataframe, so we then removed trailing and leading spaces from our dataset and reran the function to remove duplicates. 
From there we set the Trope column as our index and ran get_dummies to convert our categorical variables into dummy/indicator variables. 

Creating the Model - 
Data was clustered into 7 groups 
Clusters were appended into separate dictionaries
Duplicate title inputs were removed within each dictionary
Cluster lists were combined into a list_of_lists dictionary.
Finally a for loop was created to search for a selected movie within the different list to output a random 10 movies from the same cluster.



