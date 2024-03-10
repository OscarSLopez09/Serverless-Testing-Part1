# Let's start with a high-level overview.

I'm creating a serverless app that will be making calls to the News API website.
I will be introducing a little bit of machine learning in this app.
The app will be configured to fetch top news stories using a news API and then make calls to Amazon Comprehend service to determine the sentiment of news and categorize it as positive, negative, or neutral.
So, one thing to keep in mind.
Previously, you could run your own Python program on your machine learning program in any programming language to determine the news sentiment. Amazon created the service Amazon Comprehend, where you can pass text and determine a sentiment. Then, the news will be stored including the sentiment in Dynamo DB.
Once the news and the sentiment is stored in Dynamo DB, a user can query news by sentiment (e.g., positive, negative, neutral).
Also, we're creating a rule on Cloudwatch to trigger the Lambda function. 
