# Twitter Data Wrangling and Analysis


## Dataset
Twitter data is gathered from three different sources, wrangled, assessed, cleaned, analyzed and visualized in this project. 

WeRateDogs (@dog_rates) is a Twitter Account that rates dogs’ pictures. Its rating system is a large contributor to the account’s popularity since dogs are rated out of ten, but can have numerator higher than 10. Why? Because they’re good dogs.
As of 2021 this Twitter account has 8.9M Followers.


## There are three datasets to gather for this project.


1) An "Enhanced Archive" which contains some of the tweets of WeRateDogs Account, with some added information. This is already available enclosed in the folder accompanying this notebook.

2) An Image Predictions file to be downloaded programmatically. This file is the result of a dog-breed classifier model that classifies dog breeds in each tweet's images.

3) "Tweet_JSON" which is a dataset that will be created in this project, by querying the Twitter API to download all tweets of @rate_dogs account into a JSON file, and then load it into this notebook.

Data for missing Revenue and Budget are marked as 0.0 rather than NaN, and did not show up in early data inspection when running df.isnan() or df.info(). More than 50% of the data was 0.0 when running df.describe() which drew attention to the missing values. We can replace the missing data with the mean, but that wouldn't lead to an accurate analysis. Instead, a new set of questions is posed.

## Cleaning:
### The following steps were taken to clean the dataset before analyzing it.

•	Inner Merging of three datasets into one table, on Tweet ID.

•	Only original tweets were taken.

•	Extra columns were dropped.

•	Mistakes in Dog Names were fixed.

•	Denominators and Numerators were fixed.

•	Timestamps were converted to Date-Time format and stripped of extra characters.

•	RegEx was used to remove HTML Tags from “Sources” Column.

•	Highest Confidence prediction was taken from all three dog breed predictions for each entry.

•	Ratings with decimal values were initially incorrectly extracted. RegEx was used to extract them properly, and then they were assigned a float type.

•	Multiple dog stages were merged together.

•	ID Fields were converted to strings.

## Storing

Data was stored into a new CSV file after wrangling, before analysis.

New file is loaded and then analyzed.

Analysis description is found in enclosed document Wrangle_Act.pdf