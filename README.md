In this project, we will be working on  a serverless application. This project will be carried out fully on the AWS console.
A list of services we will be using:
1. AWS Lambda: Serverless compute service that lets you run code without provisioning or managing servers
2. API-GATEWAY: An AWS service used to create, deploy, and manage APIs at any scale.
3. Amazon S3: An object-level storage system in AWS
4. DynamoDB: a NoSQL database system managed by AWS.
5. AWS-AMPLIFY: A service for building modern web and mobile applications with serverless backends. Also, for integrating with backends service.


==================================================================================================================================================

Architecture Explanation:

Steps
1. We start by setting up the cloud9 environment:
    - log in to your AWS console and create a cloud9 environment and name it "serverless-workshop".
    - Cloud9 usually comes with nodejs pre-installed in it, you can check it by running the command:
        - node --version
        - If you can't find it then you should install it by running the:
              -  curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.2/install.sh | bash
              -  nvm install 'lts/gallium'
              -  nvm alias default 'lts/gallium'
          confirm if it's installed by running "node --version".
    - Install AWS CLI and clone the repository that contains our serverless application:
    - git clone https://github.com/aws-samples/serverless-tasks-webapp
    - pip install --user --upgrade awscli aws-sam-cli
    - cd serverless-tasks-webapp
   #By default cloud9 runs on a 2GB space but we will need to resize the space by running the script:
        bash resize.sh 20
      confirm if the size is reshaped: df -h
    - Install and configure Amplify using the AWS CLI installed on our cloud9 terminal:
       - npm i -g @aws-amplify/CLI
       - amplify configure
      
This will redirect you to log in to your AWS console, you're to create an IAM user and attach the AdministratorAccess-Amplify permission to the user to enable you to work with the AWS Amplify service, you will also be asked for an access key of your IAM user you recently created so ensure you create an access key in your console and fill it in the cloud9 terminal where you will be working.
After setting this up you will be ready to use AWS Amplify.
We will be creating a todo application where users create tasks they want to complete, each time a new task is created, A lambda function will be invoked and the newly created task will be recorded on DynamoDB. the function will also handle the response by updating the frontend UI with the newly created task. The function responds to the front-end of our application through the API gateway. This solution will be known as our backend solution and will be created using a serverless architecture model. The serverless architecture model (SAM) is an open-source framework provided by Amazon Web Services (AWS) that simplifies the process of building serverless applications. It extends AWS CloudFormation to provide a simplified way to define the Amazon API Gateway APIs, AWS Lambda functions, and Amazon DynamoDB tables needed by your serverless application. Since the SAM works with CloudFormation, we will be creating a template that will be used to build the resources of our application.




      
