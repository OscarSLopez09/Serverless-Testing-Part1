# Let's start with a high-level overview.

I'm creating a serverless app that will be making calls to the News API website.
I will be introducing a little bit of machine learning in this app.
The app will be configured to fetch top news stories using a news API and then make calls to Amazon Comprehend service to determine the sentiment of news and categorize it as positive, negative, or neutral.
So, one thing to keep in mind.
Previously, you could run your own Python program on your machine learning program in any programming language to determine the news sentiment. Amazon created the service Amazon Comprehend, where you can pass text and determine a sentiment. Then, the news will be stored including the sentiment in Dynamo DB.
Once the news and the sentiment are stored in Dynamo DB, a user can query news by sentiment (e.g., positive, negative, neutral).
Also, we're creating a rule on Cloudwatch to trigger the Lambda function. 

<img src="https://github.com/OscarSLopez09/Lambda-Serverless-App/blob/main/Images/Capture.PNG" height="80%" width="80%" alt="Disk Sanitization Steps"/>

# The AWS services used in this project:

* AWS Lambda
* Amazon Comprehend
* Dynamo DB
* Amazon API Gateway
* AWS Cloudwatch

Before we jump into the actual code, we have one pre-requisite. We get all the top news stories from the website - newsapi.org.
To call news API, we need to get an API key from them.
First, we go to https://newsapi.org and create a login account using your email, then select Get API Key.
The API Key and the account is free.

<img src="https://github.com/OscarSLopez09/Lambda-Serverless-App/blob/main/Images/newsapi.PNG" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Once you get the API we're going to be able to make calls to the API from the website newsapi.org
#

First, I'm going to build the Lambda function that is going to be used as the frontend. The lambda is going to be making call to News API 
and Amazon Comprehend service to get the sentiment, then is going to inserted in DynamoDB.

I'm going to code witch Cloud9 IDE. on the AWS console under service look for Cloud9 and select start environment and click on open.

* Create a directory with - mkdir NewsAPIReader
* Change directory -  cd NewsAPIReader
* Check the directory - ls 
* Create the lambda file using python - nano lambda_function.py
* Once the editor is open I paste the code to it
* Verify that the file was created - ls -lthr
* Install the requests external dependencies on the file - pip install requests -t *
* Zip all the files to uploaded to AWS Lambda - zip -r lambda.zip *





