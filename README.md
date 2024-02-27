**Steps to be followed:
**

Create IAM User and generate ACCESS_KEY and SECRET_KEY
Provide Administrator access to the IAM User
Fork the Repository in your organization account.
Click the repository settings and click secrets and variables and add new repository secrets one by one given below.

AWS_ACCESS_KEY_ID: <GENERATED_ACCESS_KEY>
AWS_SECRET_ACCESS_KEY: <GENERATED_SECRET_KEY>
AWS_DEFAULT_REGION: ap-south-1
AWS_REGION: ap-south-1

Open github_actions workflow and add the branch name in which you want to enable github_actions.

Open input.yaml (infra-as-code/terraform/sample-aws) and enter the details like domain_name, cluster_name, bucket_name and db_name etc.

Open egov-demo-secrets.yaml (config-as-code/environments) file and enter db_password and ssh_private_key and add public_key in github account


You can follow the below steps to generate ssh key pair:

To Generate ssh key pairs (Use either method (a) or method (b)).

a. Using online website (not recommended in prod setup. To be only used for demo setups): https://8gwifi.org/sshfunctions.jsp
b. Using openssl :

openssl genpkey -algorithm RSA -out private_key.pem openssl rsa -pubout -in private_key.pem -out public_key.pem

Now, After entering all the details, push these changes to the remote github repository. 

Open the actions in the github account, you can view the workflow has been stated and pipelines are completing successfully.

