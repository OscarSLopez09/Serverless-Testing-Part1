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

##

In this section of the project, I’m going to push the image to the Docker Hub repository. 
##

I already created a Docker Hub account, and on the account, I created a repo: Jupiter. 

1. Open my project in VS code, and right click on the jupiter-website, select integrated terminal. 
2. Login to Docker Hub with the following Command: 
* Docker login –u raphinha022 
* Input the password  
* Docker image ls  
* Docker tag jupiter raphinha022/jupiter 

<img src="https://github.com/OscarSLopez09/Deploy-Website-with-microservices/blob/main/Images/ecr0.PNG?raw=true" height="70%" width="70%" alt="Disk Sanitization Steps"/>

* Docker push raphinha022/jupiter 
* Go to Docker Hub and verify the image was uploaded.

<img src="https://github.com/OscarSLopez09/Deploy-Website-with-microservices/blob/main/Images/ecr.PNG?raw=true" height="70%" width="70%" alt="Disk Sanitization Steps"/>

##

The next step that I would do is to push the container image that I created to ECR in AWS. The AWS ECR is like Docker Hub, a service that allows the storage of container images on AWS. 
To push the container image, I would create an IAM user with programmatic access to push the container images to ECR. Once we have pushed the container image, I will use it to run Fargate containers. 
##

## IAM user creation: 
1. On AWS console look for IAM. 
2. Go to users, add users. 
3. Username: SadioMane, select access key programmatic access.

<img src="https://github.com/OscarSLopez09/Deploy-Website-with-microservices/blob/main/Images/push.PNG?raw=true" height="70%" width="70%" alt="Disk Sanitization Steps"/>

4. Set permissions, select Attach existing policies directly. 
5. Select Administrtor access and next. 

<img src="https://github.com/OscarSLopez09/Deploy-Website-with-microservices/blob/main/Images/push1.PNG?raw=true" height="70%" width="70%" alt="Disk Sanitization Steps"/>

6. Create user and download the .CSV file. 

I need to configure the keys on my PC. 

1. Open CMD and type: 
* aws configure 
* input the access key ID and Secret key ID. 
* Default region. 

<img src="https://github.com/OscarSLopez09/Deploy-Website-with-microservices/blob/main/Images/push2.PNG?raw=true" height="70%" width="70%" alt="Disk Sanitization Steps"/>
 
ECR Repository creation: 
* aws ecr create-repository –repository-name jupiter –region us-east-1 

<img src="https://github.com/OscarSLopez09/Deploy-Website-with-microservices/blob/main/Images/push3.PNG?raw=true" height="70%" width="70%" alt="Disk Sanitization Steps"/>

On AWS console, I look for ECR and veryfied that the repository had been created.

<img src="https://github.com/OscarSLopez09/Deploy-Website-with-microservices/blob/main/Images/ecr0.PNG" height="70%" width="70%" alt="Disk Sanitization Steps"/>

##
The ECR repository has been created and now I’m going to push the container image to it. 
##

1. Open my project folder in VS code. 
2. Run the following commands: 
* docker image ls 
* aws ecr get-login-password | docker login –username AWS –password-stdin URI ID 
* docker push URI ID 


<img src="https://github.com/OscarSLopez09/Deploy-Website-with-microservices/blob/main/Images/ecr01.PNG?raw=true" height="70%" width="70%" alt="Disk Sanitization Steps"/>

On AWS ECR I verify that the container image has been updated.

<img src="https://github.com/OscarSLopez09/Deploy-Website-with-microservices/blob/main/Images/ecr02.PNG?raw=true" height="70%" width="70%" alt="Disk Sanitization Steps"/>



