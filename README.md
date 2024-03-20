## Lab Overview And High Level Design

In this section of the project I'm going to create a test event and verify if the Lambda function is actually making the calls to News API
and storing the results on Dynamo DB.

This is part 2 of the project, links to the other parts below:

- [Part 1 Lambda Serverless app ](https://github.com/OscarSLopez09/Lambda-Serverless-App)
- [Part 3 Creating the backend lambda](https://github.com/OscarSLopez09/Lambda-Serverless-App-Part2)
- [Part 4 Creating API Gateway ](https://github.com/OscarSLopez09/Serverless-App-Part2-API-GW)
- [Part 5 Creating CloudWatch event](https://github.com/OscarSLopez09/Serverless-Cloudwatch-Rule)
- [Part 6 Implementing security with API keys ](https://github.com/OscarSLopez09/Lambda-Serverless-App-Security)



## Cofiguring Timeout on Lambda

First, I open the AWS consol and look for Lambda, on the lambda Console I click on the function NewsReaderAPI
the lambda code source open. 
* Now, i procedd to change the Lambda function Timeout
* Go to configurations and select edit
  
<img src="https://github.com/OscarSLopez09/Serverless-Testing-Part1/blob/main/Images/testingpart100.PNG" height="90%" width="90%" alt="Disk Sanitization Steps"/>

* On basic settings I'm going to Timeout and change the time to 2 minutes
* On execution role, select Use an existing role - DynamoDB_Comprehend
* Click save
<img src="https://github.com/OscarSLopez09/Serverless-Testing-Part1/blob/main/Images/testingpart101.PNG" height="90%" width="90%" alt="Disk Sanitization Steps"/>

By default, Lambda Timeout is 3 seconds and is going to time out the function before stops running
so, I change the timeout to allow time for the function to run properly.

## Test Event

* On the lambda code source, click on test
<img src="https://github.com/OscarSLopez09/Serverless-Testing-Part1/blob/main/Images/testingpart02.PNG" height="90%" width="90%" alt="Disk Sanitization Steps"/>

* On the Test section select create New event
* On event name type -Even1
* On the event JSON section type - {"action":"insert news"}
* Click on save
<img src="https://github.com/OscarSLopez09/Serverless-Testing-Part1/blob/main/Images/testingpart103.PNG" height="90%" width="90%" alt="Disk Sanitization Steps"/>

* Click on Test
<img src="https://github.com/OscarSLopez09/Serverless-Testing-Part1/blob/main/Images/testingpart104.PNG" height="90%" width="90%" alt="Disk Sanitization Steps"/>

* After the Executing function succeeded - click on details
* Verify the results on the section below
<img src="https://github.com/OscarSLopez09/Serverless-Testing-Part1/blob/main/Images/testingpart105.PNG" height="90%" width="90%" alt="Disk Sanitization Steps"/>

* Go to the AWS DynanoDB console and select the table - news
* Click on the refresh to check the results
* The Sentiment with the news are being store
<img src="https://github.com/OscarSLopez09/Serverless-Testing-Part1/blob/main/Images/testingpart106.PNG" height="90%" width="90%" alt="Disk Sanitization Steps"/>

Continuing the project in part 3:

- [Part 3 Creating the backend lambda](https://github.com/OscarSLopez09/Lambda-Serverless-App-Part2)







