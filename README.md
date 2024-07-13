## Deploy the application in EKS using a Helm chart fetching the image from AWS ECR

### Prerequisites:
+ Git is installed
+ Maven is installed
+ Docker is installed
+ AWS ECR repository is created
+ AWS EKS is created
+ IAM User is created
+ kubectl is installed
+ aws cli is installed
+ Helm3 is installed

### Step 1: Clone the repository
  
```xml
  github url: https://github.com/techworldwithmurali/java-application.git
```
### Step 2: build the code
```xml
mvn package
```
### Step 3: Create the repository in AWS ECR
```xml
Repository Name: web-application
```
### Step 4: Write the Dockerfile
```xml
FROM tomcat:9
RUN apt update
WORKDIR /usr/local/tomcat
ADD target/*.war webapps/
EXPOSE 8080
CMD ["catalina.sh", "run"]
```
### Step 5: Build and tag the Docker image.
```xml
docker build . --tag web-application:latest

docker tag web-application:latest 108290765801.dkr.ecr.us-east-1.amazonaws.com/web-application:latest
```
### Step 6: Login to  AWS ECR in local
```xml
aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 108290765801.dkr.ecr.us-east-1.amazonaws.com
```
### Step 7: Push the docker image to AWS ECR

### Step 8: Verify whether docker image is pushed or not in AWS ECR
```xml
docker push 108290765801.dkr.ecr.us-east-1.amazonaws.com/web-application:latest
```
### Step 9 : Create the helm chart and update the helm chart files
### Step 10: Connect to the AWS EKS Cluster
### Step 11: Install the helm chart using helm command
### Step 12: Access Java application through NodePort.


#### You have successfully Deployed the Java application in Kubernetes(AWS EKS) through Helm Chart.
