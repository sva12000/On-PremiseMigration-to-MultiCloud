
<!---
SVera is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<h1>HANDS-ON DATA MIGRATION FROM ON-PREMISE TO MULTI-CLOUD</h1>
<h>**Migratring On-Premise to Multi-Cloud Platform (Google Cloud and Amazon AWS Cloud) Using DevOps (IaC) Terraform, and Ansible scripts for faster Deployment**</h>
<h2>Description</h2>
		The project consists on Migrate The Luxxy-Covid-19 testing results system componentes Webserver (VM), Database (MySQL) and Data from the Corpore Data-Center (On-Premise), over the Multi-Cloud Platform environment (GCP and AWS) architecture. To cary out this assignment a Multi-Cloud architecture with resources running in AWS and Google Cloud Platform would be deployed using a combination of Infrastructure as Code (IaC) tools to run scripts and the GUI interface of the cloud platformS. 
The Multi-Cloud infrastructure and resources's provision will be carry out through (IaC) Terraform scripts running in AWS and Google Cloud Platforms.
		Once the infrastructure is up and running in both Cloud Platform (GCP and AWS) and the required resources have been provisioned, the Migration of Data from On-Premise over the Multi-cloud Platforms would be executed. Below there are the screenshots with the steps on how to proceed with this MultiCloud deploymennt, using IaC tools such as – Terraform – Ansible – Kubernetes and DevOps assignments.


 	DevOps

	(IaC) Infrastructure as Code tool (Declarative) Used:
		- Terraform 
  		- Ansible>

	Cloud Platform:
      	- Google Cloud Platform and Amanazon AWS Cloud Platform

	Cloud Infrastructure Solutions:
      	- SQL API
		- VM API
		
	Resources Provisioned:
		- Container Registry API
 		- Kubernetes Cluster API
    	- Kubernetes Image API
    	- Kubernetes Nodes API	
                                                                                                                                                                                            
                    
<**MultiCloud Platform – Terraform – Ansible – Docker & Kubernetes and DevOps Solution (IaC) Hands-On Project**>   

  Integration and Deployment Project in 3 Phases

  Project Deployment Solution Architecture.  

![image1 Solution Architecture](https://github.com/sva12000/SVera/assets/43139150/018fb5dc-9e3f-49aa-8bbf-b177bc44b32a)

<**PHASE 1**>
-	Access AWS console and go to IAM service
-	Under Access management, Click in "Users", then "Add users". Insert the User name terraform-en-1 and click in Next to create a programmatic user.
-	On Set permissions, Permissions options, click in "Attach policies directly" button.
-	Type AmazonS3FullAccess in Search.
-	Select AmazonS3FullAccess
-	Click in Next
-	Review all details, then click Create user.
-	**[NEW] AWS has recently changed the way to download the key.**
-	Follow the new steps:
-	Click on the user you have created.
-	After this, click on Security credentials tab.
-	Scroll down and go to Access keys section.
-	Click on Create access key
-	Select Command Line Interface (CLI) and I understand the above recommendation and want to proceed to create an access key checkbox.
-	Click Next.
-	Click on Create access key
-	Click on Download .csv file
-	After the download is finished, click on Done
	
**[TIP] Access key best practices**
-	Never store your access key in plain text, in a code repository, or in code.
-	Disable or delete access key when no longer needed.
-	Enable least-privilege permissions.
-	Rotate access keys regularly.
-	After downloading, click Done.
-	Now, rename .csv file downloaded to accessKeys.csv                                                                                                                                                  

![image2](https://github.com/sva12000/SVera/assets/43139150/6034c444-08ca-4833-b342-d988e50edad3)
**Google Cloud Platform (GCP)**
-	CLICK link below to download the mission1.zip hands-on files.
-	(https://tcb-public-events.s3.amazonaws.com/icp/mission1.zip)
-	Access GCP Console and open Cloud Shell
-	Upload **accessKeys.csv** and **mission1.zip** hands-on file to GCP Cloud Shell
-	Check if upload has been successfully completed using the command	
  ```
ls -la
  ```
-	**Hands-on files preparation**

![image3](https://github.com/sva12000/SVera/assets/43139150/48834ee1-23f4-4f18-bbe5-bee69f6568fc)

![image4](https://github.com/sva12000/SVera/assets/43139150/6e6d96da-3754-432a-b7bd-7a5d8cc53f07)

![image5](https://github.com/sva12000/SVera/assets/43139150/b863052f-1f11-47c9-a375-6e422fa500f4)

![image6](https://github.com/sva12000/SVera/assets/43139150/d5a8cfd6-2ffe-4ddc-9061-1ac97f0d8287)

•  Run the following commands to prepare AWS and GCP environment. Authorize when asked.
```
./aws_set_credentials.sh accessKeys.csv
```

![image7](https://github.com/sva12000/SVera/assets/43139150/caab2b30-21a3-4299-9ea8-d25004920039)

```
gcloud config set project <project_id>
```

![imaage8](https://github.com/sva12000/SVera/assets/43139150/e3e162fe-7922-4e40-a2e5-4edaf191c945)

**• Execute the following command**
```
./gcp_set_project.sh
```


![image9](https://github.com/sva12000/SVera/assets/43139150/4d40baa8-3626-4a1d-869e-eb73665ab26a)

![image10](https://github.com/sva12000/SVera/assets/43139150/624a0433-1861-416d-a793-d5e297db0464)

•Enable the Container Registry API, Kubernetes Engine API and the Cloud SQL API

**gcloud services enable containerregistry.googleapis.com** 

**gcloud services enable container.googleapis.com** 

**gcloud services enable sqladmin.googleapis.com**

**IMPORTANT (DO NOT SKIP):**
-	Before executing the Terraform commands:
-	Open the Google Editor and update the file tcb_aws_storage.tf replacing the bucket name with an unique name (AWS requires unique bucket names).
-	**STEPS:**
-	Open the tcb_aws_storage.tf using Google Editor
-	On line 4 of the file tcb_aws_storage.tf:
-	Replace xxxx with your name initials, using 5 letters plus 5 random numbers: Example: luxxy-covid-testing-system-pdf-en-sergio40404

![image11](https://github.com/sva12000/SVera/assets/43139150/8c24fc7e-ff90-493a-8cf5-412936a2ab73)

•Issue these commands to complete the provision infrastructure steps
```
- cd ~/mission1_en/mission1/en/terraform/
- terraform init
- terraform plan
- terraform apply
```
- Type **Yes**

- Note: It might take 15 to 25 minutes to create the Cloud SQL database, make sure to check the CloudShell to click Reconnect when the session expires (the session expires after 5 minutes of inactivity by default)
-  The warning message at the end of terraform apply command execution is not a problem, continue with the steps:

![image12](https://github.com/sva12000/SVera/assets/43139150/0a14ede0-797b-4162-95b5-bbe46dfe5b2d)

- Issue the **"ls"** command to see that the files in this folder

![image13](https://github.com/sva12000/SVera/assets/43139150/53b405c0-177a-4a64-b2a5-9a24b5b09e94)

**-terraform init**

![image14](https://github.com/sva12000/SVera/assets/43139150/e93983e4-1ff9-40f2-af4d-843ab72bbb01)

**-terraform Plan**

![image15](https://github.com/sva12000/SVera/assets/43139150/e952c2be-8bbe-4403-93a0-983bc26c9770)

**-terraform apply**

![image17](https://github.com/sva12000/SVera/assets/43139150/89737efc-b03b-42eb-a28d-7ae5ee97c3e0)

**- Type "Yes"**

![image18](https://github.com/sva12000/SVera/assets/43139150/36540a27-7953-4f27-bd34-6296b2fa056d)

**SQL Network Configuration**

•	**Once the Cloud SQL instance is provisioned, access the Cloud SQL service**

•	**Click on your Cloud SQL instance.**

•	**On the left side, under Primary Instance, click on Connections.****

•	**Go to Networking tab.**

•	**Under Instance IP assignment, select Private IP to enable**. 

o	**Under Associated networking, select "Default"**

o	**Click Set up Connection**

o	**Click on Enable API, to enable Service Networking API (if asked).**

o	**Select Use an automatically allocated IP range in your network.**

o	**Click Continue**

o	**Click Create Connection and wait a minutes until conclude. You will see the message: “Private services access connection for network default  has been successfully created.”**

•	**Under Authorized Networks, click "Add Network".**

•	**Under New Network, enter the following information:**

o	**Name: Public Access (For testing purposes only)**

o	**Network: 0.0.0.0/0**

o	**Click Done.**

o	**Click Save and wait to finish the update.** **This update may take from 10 to 20 minutes to finish**

**PS: For production environments, it is recommended to use only the Private Network for database access. ⚠️ Never grant public network access (0.0.0.0/0) to production databases.**

**You have accomplished PHASE 1 of this Project, below are the names of the Toolkit of the Multi-Cloud & DevOsp and a functional description of the TERRAFORM AND ANSIBLE Scripts used IN THE DEPLOYMENT 
OF THE ABOVE INFRASTRUCTURE:**

**Infrastructure Provisioning:**

AWS CloudShell displays an already created Terraform file named “ MAIN.TF” that would provision a VM Virtual Machine. The highlighted block will create the virtual machine.

![ImageTerraform script](https://github.com/sva12000/SVera/assets/43139150/ebfe6341-d531-4971-8f88-581d086d75bd)

 
The Terraform apply,  command when invocated it, will provision the infrastructure in a fully automated way.
 
![Terraformscript2](https://github.com/sva12000/SVera/assets/43139150/c0f23a4b-c434-4361-8c75-f2b493fcd97f)


Terraform apply is reading the main.tf file to deploy the instances or resources indicated on this file.
![TerraformScript3](https://github.com/sva12000/SVera/assets/43139150/e5294ad3-d2f9-4d21-92fa-62cb9e691f7c)
 

After a few seconds, the instance will be created on AWS  EC2 site 
![TerraformScript4](https://github.com/sva12000/SVera/assets/43139150/a34c1bb2-627c-42ad-b463-e987a3d010d3)


**Terraform configuration file to provision a VM on AWS.**
```
Live1-canivete > main.fg > provider “aws”
1	terraform {
2	  required_providers {
3	    Aws = {
4	         Source  =  “hashicorp/aws”
5	         Version =  “~> 4.16”
6	    }
7	  }
8	 
9	  Required_version = “>= 1.2.0”
10	}
11	
12	Provider “aws” {
13	    region  =  “us-west-2”
14	}
15	
16	resource “aws_instance” “app_server” {
17	   ami	          = “ami-838c94e3”
18	   Instance_type = “t2.micro”
19	
20	  Tags = {
21	      Name = “tcb-app-server1”
22	  }
23	}
```
		
**ENVIRONMENT CONFIGURATION USING**

**ANSIBLE**

It is a configuration management tool that allows you to automate all those environment configuration steps without having to connect to all those servers to do it manually.

Before you were using a note pad now you create a PlayBook.

Playbook is a configuration file with a set of tasks that you can put together for ANSIBLE can execute in parallel across multiple servers.

**Example of ANSIBLE PLAYBOOK.-**

This playbook file was created to install APACHE on a search of WEB SERVERS. 
THIS PLAYBOOK will connect to each one of the WEB Servers whether one server or a thousand servers.
It will do all the tasks at the same time in parallel.

Go there open a new connectivity to those hosts and run all the tasks and then everything that starts on line four is a task.

* so the first task that ends, 
* what’s gonna do is install and configure the latest APACHE VERSION
* And then instead of you connecting to the VM and running the uninstall for example to install a new software in a VM.
*It would now use **ANSIBLE** task to fulfill that request.
```
* Changing Directory permission 
* Copy sample index file
* Iptables:  Allow traffic on port 80” adding  IPTABLES RULES
```
All of those tasks with **ANSIBLE** in just a single shot with just one command
-You write the ANSIBLE PLAYBOOK and then you specify in which servers you want to run those set of tasks

 ![ANSIBLEscreenshot1](https://github.com/sva12000/SVera/assets/43139150/218bbb67-9a16-462c-82d2-dbca0cf58a67)






**+++++++++++++++END OF PHASE 1+++++++++++++++**



________________________________________________________________________________________________________



<**PHASE 2**>

**Amazon Web Services**
•	**Access AWS console and go to IAM service**
•	**Under Access management, Click in "Users", then "Add users". Insert the User name luxxy-covid-testing-system-en-app1 and click in Next to create a programmatic user.**

![imageA](https://github.com/sva12000/SVera/assets/43139150/177c2bc0-f8ba-4c3f-9963-2fbd79286bf3)

• **On Set permissions, Permissions options, click in "Attach policies directly" button**

![imageB](https://github.com/sva12000/SVera/assets/43139150/1b2aaa60-b994-48cd-8b63-c5b7ab03cb9d)

•	**Type AmazonS3FullAccess in Search.**

•	**Select AmazonS3FullAccess**

![imageC](https://github.com/sva12000/SVera/assets/43139150/bf00784e-c3e6-4ee1-a9a6-a4d485167797)

•	Click in Next
•	Review all details and click in Create user

![imageD](https://github.com/sva12000/SVera/assets/43139150/22820a71-c72b-4e53-9c69-a07a33fd8e36)

**Steps to create access key:**
•	Click on the user you have created.
•	Go to Security credentials tab.
•	Scroll down and go to Access keys section.
•	Click on Create access key

![imageE](https://github.com/sva12000/SVera/assets/43139150/82b7ee23-af48-4934-aae0-70892751b2bd)

- **Programmatic user created**

![image19](https://github.com/sva12000/SVera/assets/43139150/2f9a59f3-d217-4bef-acd8-ac25f6d438e3)


- **Google Cloud Platform (GCP)**
- Navigate to Cloud SQL instance and create a new user app with **password welcome123456** on Cloud SQL MySQL database

![image20](https://github.com/sva12000/SVera/assets/43139150/9c39daa5-6c54-44aa-bf26-15ad71523f88)

•	**Connect to Google Cloud Shell**

•	Download the **mission2 files** to Google Cloud Shell using the **wget command** as shown below

- 	**Copy below commands to execute above instructions.**
  
  ```
 cd ~

 mkdir mission2_en
 
 cd mission2_en
 
 wget <https://tcb-public-events.s3.amazonaws.com/icp/mission2.zip
 
 unzip mission2.zip
```

• Connect to MySQL DB running on Cloud SQL (once it prompts for the password, provide **welcome123456**)


![image21](https://github.com/sva12000/SVera/assets/43139150/d8263d70-688f-490b-89d5-7d3b81e49e13)

-**Continuation of files still being unziped**

![image22](https://github.com/sva12000/SVera/assets/43139150/4bc1a593-a554-422a-acee-a65554e42bbf)


**• Execute below command to connect to MySQL DB running on Cloud SQL (once it prompts for the password, provide welcome123456)**

```
mysql --host=<public_ip_cloudsql> --port=3306 -u app -p
```

• Enter below commands and Once you're connected to the database instance, create the products table for testing purposes

```
use dbcovidtesting;

source ~/mission2_en/mission2/en/db/create_table.sql

show tables;

exit;
```

![image23](https://github.com/sva12000/SVera/assets/43139150/9df91110-5b70-42c3-989f-0e18ac5d400e)

- Replace **<public_ip_cloudsql>** with IP Address

![image24](https://github.com/sva12000/SVera/assets/43139150/1955596a-22c4-4dcd-8172-80de1055524c)

- Provide Password **welcome123456** 

![image25](https://github.com/sva12000/SVera/assets/43139150/a60f1a6b-e572-48d0-a1da-ce56b2cba3cf)

```
use dbcovidtesting;

source ~/mission2_en/mission2/en/db/create_table.sql

show tables;

exit;
```

![image26](https://github.com/sva12000/SVera/assets/43139150/b03f4f4e-2717-4fe0-a979-42fc3b8ef680)

• Enable Cloud Build API via Cloud Shell.

- Issue below Command to enable Cloud Build API
  
```
gcloud services enable cloudbuild.googleapis.com
```

![image27](https://github.com/sva12000/SVera/assets/43139150/140cf388-f1d4-4590-8cc6-63db2c012764)



![image28](https://github.com/sva12000/SVera/assets/43139150/22880706-a047-4c16-b3eb-a5641aad0184)

• Build the Docker image and push it to Google Container Registry. Please replace the <PROJECT_ID> with your My First Project ID.

```
cd ~/mission2_en/mission2/en/app

gcloud builds submit --tag gcr.io/<PROJECT_ID>/luxxy-covid-testing-system-app-en
```

![image29](https://github.com/sva12000/SVera/assets/43139150/64f7dfac-5785-4a2b-aa2a-08d9589af28c)


**run ls -la command**
![image30](https://github.com/sva12000/SVera/assets/43139150/28dcacba-5ecb-41d2-83ad-c1e88372ab4c)

 Run the command below
 
**gcloud builds submit --tag gcr.io/<PROJECT_ID>/luxxy-covid-testing-system-app-en**

![image31](https://github.com/sva12000/SVera/assets/43139150/a1368dc5-8ceb-427a-8db4-03f8b3f506ca)

**Files still been pushed**
![image32](https://github.com/sva12000/SVera/assets/43139150/63b5001c-91a8-4375-8c2e-a79daa86e557)


**After all the files are pushed you go and search for container Registry Blade, select IMAGE and you will see the Docker container created on it, click on it and you will see the docker image on the next windows.**

- **See Docker images already pushed in to Google Container Registry**
  
![image33](https://github.com/sva12000/SVera/assets/43139150/e5cc9e8a-ca7e-4883-9734-0d86fd5ec55f)


• **Open the Cloud Editor and edit the Kubernetes deployment file (luxxy-covid-testing-system.yaml) and update the variables below.**

- On line 33 in red with your <PROJECT_ID> on the Google Container Registry path.

- On line 42 AWS Bucket name, AWS Keys (**open file luxxy-covid-testing-system-en-app1.csv and use Access key ID on line 44 and Secret access key, on line 46)** and from

- **Cloud SQL Database page copy Private IP on line 48.**

  To acomplish the above in the open editor page navegate to the folder to access the kubernetes forlder and click on it. follow below instructions.

  
cd ~/mission2/en/kubernetes

luxxy-covid-testing-system.yaml

image: gcr.io/**<PROJECT_ID>/**luxxy-covid-testing-system-app-en:latest
...
	- name: AWS_BUCKET
 
          value: "**luxxy-covid-testing-system-pdf-en-xxxx**"
	  
        - name: S3_ACCESS_KEY
	
          value: "**xxxxxxxxxxxxxxxxxxxxx**"
	  
        - name: S3_SECRET_ACCESS_KEY
	
          value: "**xxxxxxxxxxxxxxxxxxxx**"
	  
        - name: DB_HOST_NAME
	
          value: "**172.21.0.3**"

   REPLACE <PROJECT_ID> word with your actually project_ID.

- image: gcr.io/<PROJECT_ID>/luxxy-covid-testing-system-app-en:latest
  
![image34](https://github.com/sva12000/SVera/assets/43139150/144ee82c-c1d8-492f-afad-093c7404ec84)


On line 42 replace the xxxx

"**luxxy-covid-testing-system-pdf-en-xxxx**"

![image35](https://github.com/sva12000/SVera/assets/43139150/b8b9c79d-e241-4ff0-bff6-ac01d50610af)



![image36](https://github.com/sva12000/SVera/assets/43139150/45c4f4a6-dbf1-48f5-8d8d-5b9887513ec5)

Copy to line 44 and 46, AWS Bucket S3 **Access Key ID and S3 Secret Access Key** from the luxxy-covid-testing-system-en-app1.csv file downloaded when the user was created and 


![image37](https://github.com/sva12000/SVera/assets/43139150/eb2586a3-9bc1-4d74-82fc-6280d2ad9518)


- **From CLOUD SQL page copy the private IP address of the instance and add it to line 48 under the name: DB_HOST_NAME**

![image38](https://github.com/sva12000/SVera/assets/43139150/fe97478d-6c13-4589-bade-7c4ee9ee1e5a)


Connect to the GKE (Google Kubernetes Engine) cluster via Console (click RUN IN CLOUD SHELL) Follow below steps** 

**Steps:**

**On Kubernetes Engine menu page > Click on CONNECT tab**

**On the pop up CONNECT TO THE CLUSTER page > Click on RUN IN CLOUD SHELL**

![imageConnecttoGKE](https://github.com/sva12000/SVera/assets/43139150/0586427d-aa53-4bb0-8071-5b20dbb98a36)

**PRESS ENTER**

![image39](https://github.com/sva12000/SVera/assets/43139150/ac1f95dd-9add-456f-8e86-244eb663c2b1)


- **You can see you are connected to my Kubernetes-cluster**

![image40](https://github.com/sva12000/SVera/assets/43139150/3e25b912-9f4c-4c7d-9ef2-9c3e32a9a972)


- Just run the “kubectl get nodes” command and you will see how many nodes you have inside your Kubernetes cluster it is gonna return something or it will give you an error.

- Right now you do not have any nodes available in the cluster. It is gonna actually deploy it because we are using an auto-pilot cluster.
  
- You re going to see the deployed the application, but it is working.

- So now we are going to go ahead and deploy our application in the next step


Run **"kubectl get nodes"** command to see how many nodes are running make sure you are in the right path **/mission2_en/mission2/en/app**
```
kubectl get nodes
```

![image41](https://github.com/sva12000/SVera/assets/43139150/8ffdbd2e-bbaa-438c-81e4-1433054cccb5)

- Deploy the application Luxxy in the Cluster, but fisrt change to the Kubernetes folder.
```
cd ~/mission2_en/mission2/en/kubernetes
```

![image42](https://github.com/sva12000/SVera/assets/43139150/06240037-a52d-422e-a043-7479c1555f14)

The next command will deploy the application inside of the cluster.     

– The reason for the warning is the Kubernetes cluster on Google Cloud is very cost-efficient.

- If you don’t have any application running in the cluster, it will not hold any resources in there.

- As soon as you deploy the first application the Kubernetes is going to add the number of nodes to the cluster.
                                                                                                                                                                                                          – So the node can server your application.


**Warning:** autopilot-default-resources-mutator: Autopilot updated Deployment default/luxxy-covid-testing-system: defaulted unspecified resources for containers [luxxy-covid-testing-system]

  (see http://g.co/gke/autopilot-defaults) deployment.apps/luxxy-covid-testing-system created service/luxxy-covid-testing-system configured

• to Deploy the application Luxxy in the Cluster Use **kubectl apply -f**  command.

```
kubectl apply -f luxxy-covid-testing-system.yaml
```

![image43](https://github.com/sva12000/SVera/assets/43139150/0d67ab0b-2fde-4f9f-b18b-e34256747f48)

Next we click on Workload on Kubernetes Engine Blade and you see under Overview the name and status are OK deployment 1/1 pods, namespace as default, and the cluster.  

–  If you get a message like “ It was not possible to deploy the application”                                                                          

-  The reason could be that Kkubernetes is going to outscale it.

-  If you look in the memory…. Meaning the Kubernetes is updating itself. So in a few minutes the application will up and running.

-  Click on services & ingress

-  You see it also creating the service endpoint

-  The external load balancer that we can test the application remotely

-  Next on cloud shell terminal type “ kubectl get nodes” command.

- You can see Kubernetes Cluster added a new node to serve the application that we have requested. This behavior is not the same with all the cloud providers

- Next on services & ingress click on enpoint Ip address and the web page application will show up

-   meaning this application is communicating with Google Cloud SQL on Google cloud also is communicating with AWS bucket sitting on AWS


•	Get the Public IP and test the application (CLICK HERE to download COVID-19 Testing result sample https://tcb-events.s3.amazonaws.com/icp/mission2.zip ). 

-	Search for GKE, click on Services & Ingress, and then on Endpoints address:port  IP address

-	It will open Luxxy - Luxury Hotels & Resorts COVID-19 Testing Status System WEBSITE


•	You should see the Webapp up & running! Congrats!

CLICK THE **VIEW GUEST RESULTS** on the top upper right corner of the page to display the RECORDS PAGE


![image45](https://github.com/sva12000/SVera/assets/43139150/a7ee6f26-1063-4afe-882d-3511e1882648)


**If you click on any link record it will not display because the PDF files has not been synch yet to the Amazon AW S3 Bucket yet. That will be done in the next taks (TASK3)**


![image46](https://github.com/sva12000/SVera/assets/43139150/8bd9b5e9-d58c-4b0f-89cc-02587f57b3cc)


**Migration Done so far is showed up in the Graphyc below**

![imagemission2Donesofar](https://github.com/sva12000/SVera/assets/43139150/99b397fa-21d1-4174-81c8-0609b36a67af)

**You have completed Phases 2**  

---------



<**PHASE 3**>

- #NEXT MIGRATION OF BOTH DATABASES'S DATA TO SOLUTION ARCHITECTURE#

  ![ImageTask3Photo](https://github.com/sva12000/SVera/assets/43139150/278dfcd1-4002-4b78-a10d-2c68f7838820)

  

**- Google Cloud Platform - Database Migration steps**

•	Connect to Google Cloud Shell

•	Download the dump using wget

```
cd ~

mkdir mission3_en

cd mission3_en

wget https://tcb-public-events.s3.amazonaws.com/icp/mission3.zip

unzip mission3.zip
```

![IMAGETASK3A](https://github.com/sva12000/SVera/assets/43139150/b40e552d-be55-4f9a-a160-f88f57e32450)


Connect to Cloud SQL MySQL database instance by running the following command. Make sure to add the SQL INSTANCE host public IP address.

```
mysql --host=<public_ip_address> --port=3306 -u app -p
```

![ImageTASK3B](https://github.com/sva12000/SVera/assets/43139150/4b21e4b1-6ca5-461e-a910-95323a361c7f)


Import the dump on Cloud SQL running the following command:

```
se dbcovidtesting;

source ~/mission3_en/mission3/en/db/db_dump.sql
```


![ImageTask3C](https://github.com/sva12000/SVera/assets/43139150/0a8fa374-ce5a-4ee3-a807-119355f9af56)


Check if the data got imported correctly run the following command

```
select * from records;
```


![ImageTask3D](https://github.com/sva12000/SVera/assets/43139150/f3005ec3-1b06-4339-87eb-c61b9285e9b7)


Type the command below to :

```
exit;
```

![ImageTask3E](https://github.com/sva12000/SVera/assets/43139150/8054443f-b345-471b-a88d-21d46106db90)


-  We are going to migrate both databases including the PDF data, which has the COVID-19 testing results from the On-premises application server to the S3 Bucket

**-  Amazon Web Services - PDF Files Migration steps**
   
•	Connect to the AWS Cloud Shell

•	Download the PDF files

```
mkdir mission3_en

cd mission3_en

wget https://tcb-public-events.s3.amazonaws.com/icp/mission3.zip
```

```
unzip mission3.zip
```


**mkdir mission3_en**
![image47](https://github.com/sva12000/SVera/assets/43139150/2198da91-4a5f-44d7-b190-9b066ca434cd)


**cd mission3_en**

![image48](https://github.com/sva12000/SVera/assets/43139150/789b1826-311c-4ae4-80ac-28be65210f88)


**wget https://tcb-public-events.s3.amazonaws.com/icp/mission3.zip**


![image50](https://github.com/sva12000/SVera/assets/43139150/2a2cf5bd-6ec8-4162-89fe-1810338c616a)

**unzip mission3.zip**

![image51](https://github.com/sva12000/SVera/assets/43139150/27966163-c530-4f5f-a241-cffec3433af5)


Sync PDF Files with your AWS S3 used for COVID-19 Testing Status System. Replace the bucket name with yours.

Run these commands to accomplish that.

```
cd mission3/en/pdf_files

aws s3 sync . s3://luxxy-covid-testing-system-pdf-en-xxxx
```

![image52](https://github.com/sva12000/SVera/assets/43139150/53454f73-9d2e-4d29-8e03-00b59b7eb3b3)

**aws s3 sync . s3://luxxy-covid-testing-system-pdf-en-xxxx**

![image53](https://github.com/sva12000/SVera/assets/43139150/88f5cde8-3ce4-45b8-b345-e562de2a6368)

**Still Synch and uploading PDF files**

![image54](https://github.com/sva12000/SVera/assets/43139150/4952f4b3-6276-4919-bbab-1fb57081e1e9)

**All PDF files are synch and you can see them in the AmazonS3 > Buckets**

![image55](https://github.com/sva12000/SVera/assets/43139150/1f0dfefe-ac32-4c14-9afa-96fd183f964a)

• **Test the application.**

- Upon migrating the data and files, you should be able to see the entries under “View Guest Results” page.
  
- Click any link and should show the information on the pdf file migrated to you aws S3 bucket.

![image56](https://github.com/sva12000/SVera/assets/43139150/02c90f7f-a710-4a9d-84d0-190c93f46fda)

**Pdf file info is displyed**

![ImageTask3H](https://github.com/sva12000/SVera/assets/43139150/ad1ae267-bd0e-4fab-a187-895a9fd3e952)


#**CONGRATULATIONS YOU HAVE SUCESSFULY ACCOMPLISHED THE PROJECT!**#


  




















