# MLflow-Basic-Demo



## For Dagshub:

MLFLOW_TRACKING_URI=https://dagshub.com/entbappy/MLflow-Basic-Demo.mlflow \
MLFLOW_TRACKING_USERNAME=safnas \
MLFLOW_TRACKING_PASSWORD=6824692c47a369aa6f9eac5b10041d5c8edbcef0 \
python script.py



```bash

export MLFLOW_TRACKING_URI=https://dagshub.com/entbappy/MLflow-Basic-Demo.mlflow

export MLFLOW_TRACKING_USERNAME=safnas 

export MLFLOW_TRACKING_PASSWORD=6824692c47a369aa6f9eac5b10041d5c8edbcef0


```


# MLflow on AWS

## MLflow on AWS Setup:

1. Login to AWS console.
2. Create IAM user with AdministratorAccess
3. Export the credentials in your AWS CLI by running "aws configure"
4. Create a s3 bucket
5. Create EC2 machine (Ubuntu) & add Security groups 5000 port

Run the following command on EC2 machine
```bash
sudo apt update

sudo apt install python3-pip

sudo apt install pipenv

sudo apt install virtualenv

mkdir mlflow

cd mlflow

pipenv install mlflow

pipenv install awscli

pipenv install boto3

pipenv shell


## Then set aws credentials
aws configure

#connect mlflow with s3
mlflow server -h 0.0.0.0 --default-artifact-root s3://mlflow-tracking-buc25 --allowed-hosts "*"

#Set EC2 security 
open Public IPv4 DNS to the port 5000

AWS -> EC2 -> Copy Public DNS
---> Public DNS:Port Number  = ec2-13-50-111-248.eu-north-1.compute.amazonaws.com:5000

while searching it on browser use ---> http not https
// http://ec2-13-50-111-248.eu-north-1.compute.amazonaws.com:5000



