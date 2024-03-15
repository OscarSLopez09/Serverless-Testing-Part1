## Lab Overview And High Level Design

In this section of the project I'm going to create a test event and verify if the Lambda function is actually making the calls to News API
and storing the results on Dynamo DB.

## Setup

First, I open the AWS consol and look for Lambda, on the lambda Console I click on the function NewsReaderAPI
the lambda code source open. 
* Now, i procedd to change the Lambda function Timeout
* Go to configurations and select edit
<img src="https://github.com/OscarSLopez09/Serverless-Testing-Part1/blob/main/Images/testingpart100.PNG" height="80%" width="80%" alt="Disk Sanitization Steps"/>
* On basic settings I'm going to Timeout and change the time to 2 minutes

* On execution role, select Use an existing role - DynamoDB_Comprehend
* Click save
By default, Lambda Timeout is 3 seconds and is going to time out the function before stops running
so, I change the timeout to allow time for the function to run properly.

<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>







