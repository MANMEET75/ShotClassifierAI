# ShotClassifierAI
I have created a sophisticated deep learning model named "ShotClassifierAI" to accurately predict different types of cricket shots such as sweep, drive, leg glance-flick, and pull shot. This model has been meticulously trained using VGG16 as a base model.To ensure smooth deployment, I have seamlessly integrated this model into a comprehensive end-to-end solution, making use of AWS ECR and an EC2 instance for efficient and effective deployment.

I initiated the process by setting up a repository on GitHub. Subsequently, I acquired a comprehensive dataset from Kaggle encompassing four distinct types of cricket shots: sweep, pull shot, legglance-flick, and drive.
<img src="sampleV.gif">
# Dataset URL:
[Click here to download data](https://github.com/MANMEET75/ShotClassifierAI/raw/main/data/Cricket.zip)


Next, I meticulously constructed the comprehensive structure essential for implementing the end-to-end model. This involved crafting the necessary code segments within the "template.py" file, which forms the backbone of the entire system.

I meticulously documented all the crucial packages in the requirements.txt file, ensuring the inclusion of all necessary dependencies. Additionally, I developed a setup.py file to store important metadata. Finally, I effortlessly installed the packages, guaranteeing a seamless integration within the environment.



Next, I dedicated my attention to the logging module, enabling comprehensive tracking of the application's workflow. Subsequently, I focused on the development of the utils.py file, where I implemented reusable code snippets that can be conveniently utilized throughout the entire application.

# Research Environment

Within the research environment, I conducted thorough experimentation using Jupyter Notebook. Initially, I focused on data ingestion, successfully reading the dataset from GitHub. Subsequently, I experimented with various base models, meticulously selecting the one that exhibited superior accuracy and performance metrics. Additionally, I conducted experiments pertaining to the preparation of callbacks, training procedures, and eventually transformed my code into a modular structure for enhanced organization and maintainability.

I meticulously followed a structured workflow to transform my notebook code into modular code, ensuring its stability and compatibility in the production environment.
# Development Environment
## Workflows

1. Update config.yaml
2. Update secrets.yaml [Optional]
3. Update params.yaml
4. Update the entity
5. Update the configuration manager in src config
6. Update the components
7. Update the pipeline 
8. Update the main.py


# How to run?
### STEPS:

Clone the repository

```bash
git clone https://github.com/MANMEET75/ShotClassifierAI.git
```
### STEP 01- Create a conda environment after opening the repository

```bash
conda create -n ShotClassifierAI python==3.8 -y
```
Activate the environment
```bash
conda activate ShotClassifierAI
```


### STEP 02- Install the requirements
```bash
pip install -r requirements.txt
```

### STEP 03- Run the application
```bash

python app.py
```

Now,
```bash
open up you local host and port
```


# Production Environment
### AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

	#with specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
## 3. Create ECR repo to store/save docker image
    - Save the URI: 566373416292.dkr.ecr.us-east-1.amazonaws.com/catdog

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optinal

	sudo apt-get update -y

	sudo apt-get upgrade
	
	#required

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
# 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os> then run command one by one


# 7. Setup github secrets:

    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME = simple-app

Enjoy Coding!
