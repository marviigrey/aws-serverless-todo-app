In this project, we will be working on  a serverless application. This project will be carried out fully on the AWS console.
A list of services we will be using:
1. AWS Lambda: Serverless compute service that lets you run code without provisioning or managing servers
2. API-GATEWAY: An AWS service used to create, deploy, and manage APIs at any scale.
3. Amazon S3: An object-level storage system in AWS
4. DynamoDB: a NoSQL database system managed by AWS.
5. AWS-AMPLIFY: A service for building modern web and mobile applications with serverless backends. Also, for integrating with backends service.


==================================================================================================================================================
Architecture Explanation:

----------------------------------------------------------------------------------------------
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
    - Install AWS CLI and clone the repository:
    - git clone https://github.com/aws-samples/serverless-tasks-webapp
    - pip install --user --upgrade awscli aws-sam-cli
    - cd serverless-tasks-webapp
   #By default cloud9 runs on a 2GB space but we will need to resize the space by running the script:
        bash resize.sh 20
      confirm if the size is reshaped: df -h
    - we log into the cloud9 terminal and create an IAM user for Amplify.
    - Ne
