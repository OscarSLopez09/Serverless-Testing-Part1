# Deploying the jupiter website using microservices!



In this project, I'm deploying a website using microservices, including the VPC infrastructure where is going to run. Services used in this project are as follows:

* Create a Dockerfile. 
* Create repository on Docker Hub. 
* Create an Amazon ECR Repository. 
* Create an Amazon ECS Cluster. 
* Create a Task Definition. 
* Create a Service. 
* Build AWS VPC from scratch.  
* Create Nat Gateways.  
* Create Security Groups. 
* Create application load balancer.  
* Create a record set in Route 53.  
* Register an SSL certificate in AWS certificate manager.  
* Create an HTTPS Listener for the application load balancer. 
##

The Dockerfile is a text document that contains all the commands that we’ll use to create the container image. 
##
1.  To start, I open VS code and select the folder (Docker-project) the repositor clone. Now I’m creating a new folder named: Jupiter-website, and then I create a file: Dockerfile. 
2. Copy and paste the commands that I’m using to create the Dockerfile to VS code. 

<img src="https://github.com/OscarSLopez09/Deploy-Website-with-microservices/blob/main/Images/dockerfile.PNG" height="70%" width="70%" alt="Disk Sanitization Steps"/>

3. Once, I checked that all the commands were good I saved them.  
4. Click on source control tab and commit the changes. 

<img src="https://github.com/OscarSLopez09/Deploy-Website-with-microservices/blob/main/Images/dockerfile1.PNG?raw=true" height="70%" width="70%" alt="Disk Sanitization Steps"/>

5. I checked my work by going to GitHub and they’re successfully uploaded. 

<img src="https://github.com/OscarSLopez09/Deploy-Website-with-microservices/blob/main/Images/dockerfile2.PNG?raw=true" height="70%" width="70%" alt="Disk Sanitization Steps"/>

##
In this section of the project, I’m going to create the image using the Dockerfile I uploaded. 
##

1. Open my project in VS code, and right click on the jupiter-website, select integrated terminal. 
2. Input the following commands: 
* ls 
* Docker build –t jupiter . 

<img src="https://github.com/OscarSLopez09/Deploy-Website-with-microservices/blob/main/Images/create.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>

* Docke image ls – to check if the image has been created. 

<img src="https://github.com/OscarSLopez09/Deploy-Website-with-microservices/blob/main/Images/create1.PNG?raw=true" height="70%" width="70%" alt="Disk Sanitization Steps"/>

