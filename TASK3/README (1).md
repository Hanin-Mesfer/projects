Dataset

This project focuses on the sentiment analysis of  Twitter  Airline (https://www.kaggle.com/crowdflower/twitter-airline-sentiment) . By using machine learning 

text: The tweet text.
airline_sentiment: The sentiment label for each tweet.
airline_sentiment_confidence: The confidence score for the sentiment classification.

Code Functionality

Data Import and Initial Preprocessing:

The tweet data is loaded from a CSV file, and tweets with confidence levels below 0.6 are removed.
Text Cleaning:

Function cleaning(text) is applied to preprocess each tweet. It:
Converts text to lowercase.
Removes URLs, special characters, and emojis.
Expands common contractions (e.g., "don't" becomes "do not").
Stop Words Removal:

Stop words (common words like "the" and "is" that don't contribute to sentiment analysis) are removed from the cleaned text.
Frequent Word Analysis:

Counts the top 10 most frequent words and visualizes them in a horizontal bar chart.
Code Snippet for Visualization
The code uses plotly to generate an interactive bar chart:

python

px.bar(temp, x="count", y="word", title='Common Words in Text', orientation='h', width=700, height=700)
Usage
To run this code, make sure you have the required libraries installed. Execute the code in a Python environment (e.g., Jupyter Notebook or a Python script).


# Import the necessary libraries and load data
import pandas as pd
import matplotlib.pyplot as plt
import plotly.express as px

# Additional imports and data processing
# ...

Visualization

px.bar(temp, x="count", y="word", title='Common Words in Text', orientation='h', width=700, height=700)







