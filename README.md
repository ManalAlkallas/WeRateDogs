# WeRateDogs Data Wrangling Project

## Introduction
This project is part of the data wrangling section of the Udacity Data Analyst Nanodegree program and is primarily focused on wrangling data from the [WeRateDogs](https://twitter.com/dog_rates), which is a Twitter account that rates people's dogs with a humorous comment about the dog. The rating denominator is usually 10, however, the numerators are usually greater than 10. This aspect was not cleaned as it is part of the humor and popularity of WeRateDogs.

- The required softwares:
    1. Jupyter Notebook
    2. The required packages (libraries) need to be installed. 
        - pandas
        - NumPy
        - requests
        - tweepy
        - json
    3. A text editor, like [Sublime](https://www.sublimetext.com/)
        
## Project Goal
For this project, we only wanted original ratings (no retweets) that have images. Not all of the original tweets in the dataset are dog ratings and some are retweets.

Fully assessing and cleaning the entire dataset would require exceptional effort so only a subset of its issues (eight quality issues and two tidiness issues at minimum) needed to be assessed and cleaned.

The tasks for this project were:
- Data wrangling, which consisted of:
  - Gathering data
  - Assessing data
  - Cleaning data
- Storing, analyzing, and visualizing the wrangled data
- Reporting on my data analyses and visualizations (act_report.pdf)

## The Datasets
1. **Enhanced Twitter Archive** The WeRateDogs Twitter archive contains basic tweet data for all 5000+ of their tweets, but not everything. One column the archive does contain though: each tweet's text, which Udacity used to extract rating, dog name, and dog "stage" (i.e. doggo, floofer, pupper, and puppo) to make this Twitter archive "enhanced." Of the 5000+ tweets, Udacity provided a  filtered dataset for tweets with ratings only (there are 2356).</br>

Enhanced Twitter Archive is extracted  programmatically, but it was not a  very good job. The ratings probably aren't all correct. Same goes for the dog names and probably dog stages too. I need to assess and clean these columns.

2. **Additional Data via the Twitter API** The provided Twitter archive lacked some useful information: retweet count and favorite count. I used the tweet IDs to query the Twitter API for each tweet's JSON data using Python's Tweepy library and stored each tweet's entire set of JSON data in a file called tweet_json.txt. I then read the txt file line by line into a pandas DataFrame only including the desired variables; retweet count and favorite count.

3. **Image Predictions File** Udacity also provided a link to image_predictions.tsv which should be downloaded programatically using the Requests library.
This dataset ia  a table full of image predictions alongside each tweet ID, image URL, and the image number that corresponded to the most confident prediction 

- Image Predictions table columns:
    - tweet_id 
    - p1 is the algorithm's #1 prediction for the image in the tweet 
    - p1_conf is how confident the algorithm is in its #1 prediction 
    - p1_dog is whether or not the #1 prediction is a breed of dog 
    - p2 is the algorithm's second most likely prediction 
    - p2_conf is how confident the algorithm is in its #2 prediction
    - p2_dog is whether or not the #2 prediction is a breed of dog
 

## Key Points
- Key points to keep in mind when data wrangling for this project:
    - I only want original ratings (no retweets) that have images. Though there are 5000+ tweets in the dataset, not all are dog ratings and some are retweets.
    - Assessing and cleaning at least 8 quality issues and at least 2 tidiness issues in this dataset.
    - Cleaning includes merging individual pieces of data according to the rules of tidy data.
    - The fact that the rating numerators are greater than the denominators does not need to be cleaned. This [unique rating system](https://knowyourmeme.com/memes/theyre-good-dogs-brent) is a big part of the popularity of WeRateDogs.
    - I do not need to gather the tweets beyond August 1st, 2017.

        
