# The EZ-Screener App

The EZ-Screneer App is an application developed by team 21 of the Holy Hack Hackathon on the 18-19 of March 2022. 

## Why?  
For a company like Bank Van Breda, it’s very important to get a quick idea 
about the commercial potential of a new customer. One important factor is 
how a company is currently performing, and how this is perceived in its 
market. 
Why do I suffer

 
## What?  
We would like you to build an application that searches the internet for 
publicly available information about a company, and then displays its main 
activity, and a simple ‘Sentiment’ index, ranging form 1 (very negative 
sentiment) to 10 (very positive). It would also be useful to be able to drill 
down into the reasons behind the final result. The user can also give 
feedback about the result, so that the system can learn over time. 
 
## How?  
The application can be a desktop or mobile app, or preferably both. In the 
latter case, code reuse is a big bonus. The app should communicate with 
a microservices based backend. 


## Sentiment Analysis Model and Rest API

To provide a grade to a company, we built a sentiment analysis model via the Bag of Words approach within Natural Language Processing (NLP). Each text in the data is broken down by the frequency count that it has. We then labelled a small amount of data (positive or negative), so that we can train a Support Vector Machine (SVM) model on it.

We also built and deployed the model via a rest API on Heroku. You can access the predict endpoing as follows:

ENDPOINT URL = https://bow-api.herokuapp.com/

Example Parameters = {"text": "tesla is a very great company"}

Example Response = {
    "id": "67",
    "sentiment": "0",
    "text": "tesla is a very great company"
}

A sentiment of 0 indicates a positive article, while a sentiment of -1 indicates a negative article.