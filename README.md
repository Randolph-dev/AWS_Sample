# AWSSampleApp

# aws_code_deploy
## Steps for AWS Sample App
 1.  **Create IAM Roles - CodeDeploy & EC2CodeDeploy**
 1.  **Create EC2 instance with the following software packages should install**<br/>
 1.  **Choose AMI: Amazon Linux 2**<br/>
     ![alt text](https://github.com/prabhakar2020/aws_code_deploy/blob/master/AMI.png)<br/>
 1.  **Choose AMI role as EC2CodeDeploy**<br/>
     ![alt text](https://github.com/prabhakar2020/aws_code_deploy/blob/master/ConfigureInstance.png)<br/>
 1.  **Choose User Data: for installing required packages.**<br/>
 2.  ```
     #!/bin/bash
     sudo yum -y update
     sudo yum -y install ruby
     sudo yum -y install wget
     cd /home/ec2-user
     wget https://aws-codedeploy-eu-central-1.s3.eu-central-1.amazonaws.com/latest/install
     sudo chmod +x ./install
     sudo ./install auto
     sudo yum install -y python-pip
     sudo pip install awscli
     ```
     
     ![alt text](https://github.com/prabhakar2020/aws_code_deploy/blob/master/UserData.png)<br/>
 1.  **Security groups: which enable port SSH port 22 and HTTP 80 for application**<br/>
     ![alt text](https://github.com/prabhakar2020/aws_code_deploy/blob/master/configureSecutiryGroup.png)<br/>     
 1.  **Add tags to your EC2 instance**<br/>
     ![alt text](https://github.com/prabhakar2020/aws_code_deploy/blob/master/addTags.png)<br/>
 1.  **Launch instance**<br/>
 1.  **Goto CodeDeploy Create Application**<br/>
 1.  **Create a DeploymentGroup**<br/>
 1.  **Go to CodePipeline and create a new pipeline**<br/>
 1.  **Choose the source provider as CodeCommit or Github**<br/>
 1.  **Add source, build, deploy stages**<br/>
 1.  **Try all the relevant AWS tools e.g. Cloud9, CodeCommit, CodeBuild, CodeDeploy and CodePipeline 
 (No worries if some of these do not work instantly we can always try later :)**<br/>
 1.  **You can verify if codedeploy is running from this command in EC2 instance**
     ```sudo service codedeploy-agent status```

**Working app**: \
 You should see the working application from here after succesussfully using above AWS services: http://3.122.59.14/

**References**: \
Please read some of these references \
 https://aws.amazon.com/codecommit/ \
 https://aws.amazon.com/codepipeline/ \
 https://aws.amazon.com/codebuild/ \
 https://aws.amazon.com/codedeploy/ \
 https://aws.amazon.com/cloud9/ \
 https://docs.aws.amazon.com/codedeploy/latest/userguide/instances-ec2-create.html  \
 https://docs.aws.amazon.com/codedeploy/latest/userguide/getting-started-create-iam-instance-profile.html#getting-started-create-iam-instance-profile-console \
https://docs.aws.amazon.com/codedeploy/latest/userguide/codedeploy-agent-operations-install-linux.html

 
**Troubleshooting**: \
https://forums.aws.amazon.com/message.jspa?messageID=758542  \
https://forums.aws.amazon.com/thread.jspa?threadID=181032  
