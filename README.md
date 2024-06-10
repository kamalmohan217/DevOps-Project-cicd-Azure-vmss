# DevOps-Project-cicd-Azure-vmss
![image](https://github.com/kamalmohan217/DevOps-Project-cicd-Azure-vmss/assets/128888356/4817305f-ed31-4e2f-b52d-06a32df05138)
For the present scenario I am deploying a web application in Azure vmss using Azure DevOps. The infrastructure has been created using terraform script as present in this repository. Initially a Golden Image is created using packer which runs through the shell-script create-infra.sh. This shell script creates an Azure Compute Gallery and Image definition in Azure Compute Gallery using the Azure CLI. Tomcat has been installed in Golden AMI using Ansible. For creation of Golden Image I have used packer. 
<br><br/>
For Deployment of war file which is created during the build stage as shown in the Architecture diagram above, Image versions has been created I have named it as Release Images. These Image versions will be stored in the Azure Compute Gallery and Azure vmss will be updated with these Image versions. Creation of Release Images and updating vmss with these image versions is initiated by shell script, I named it as create-infra.sh. This shell script, Ansible playbook, template.json to create Release Image versions and azure-pipelines.yml which will be used for deployment are present in Azure Repos as shown in the screenshot below.
![image](https://github.com/kamalmohan217/DevOps-Project-cicd-Azure-vmss/assets/128888356/313204c1-06c7-4592-ad5b-0ec769179a42)
<br><br/>
For storing Artifacts, Azure Artifacts has been used and pom.xml should be updated as shown in the screenshot below.
![image](https://github.com/kamalmohan217/DevOps-Project-cicd-Azure-vmss/assets/128888356/164ee379-d1f9-4044-9d47-8f3a0c0aed1d)
![image](https://github.com/kamalmohan217/DevOps-Project-cicd-Azure-vmss/assets/128888356/c99f4e63-9d8d-49be-8c9f-7b7ecedc20c1)
<br><br/>
Service Connection has been created for SonarQube and Maven-Feed as shown in screen-shot attached below.
![image](https://github.com/kamalmohan217/DevOps-Project-cicd-Azure-vmss/assets/128888356/856fed74-520c-4ca0-9220-6d53eb526aea)
<br><br/>
Record Set entry in Azure DNS Zones for Application Gateway has been shown in screen-shot attached blow.
![image](https://github.com/kamalmohan217/DevOps-Project-cicd-Azure-vmss/assets/128888356/9202ed90-d1a8-4890-8c17-9c3b907e1026)
<br><br/>
Finally different Release Image versions has been created and deployed to Azure vmss as shown in the screenshots attached below.
![image](https://github.com/kamalmohan217/DevOps-Project-cicd-Azure-vmss/assets/128888356/1956c998-f59e-4387-9243-830169911948)
![image](https://github.com/kamalmohan217/DevOps-Project-cicd-Azure-vmss/assets/128888356/423f72a8-656f-49c8-a8f4-e81d00556c73)
<br><br/>
For Azure DevOps Agent I have used single-hosted agent on which I have installed Java 11, Maven and Packer.
<br><br/>
Multiple versions of Release Images will be present in Azure Compute Gallery. Screenshot of the same has been attached below.
<br><br/>
![image](https://github.com/kamalmohan217/DevOps-Project-cicd-Azure-vmss/assets/128888356/b41d1995-bf2d-4b59-b85c-b60a4744b7ca)
![image](https://github.com/kamalmohan217/DevOps-Project-cicd-Azure-vmss/assets/128888356/eaedb3c3-a414-4d63-88af-eb883a89a0cb)
<br><br/>
After Deployment you can check the current image version from the console also as shown in the screenshot attached bwlow.
![image](https://github.com/kamalmohan217/DevOps-Project-cicd-Azure-vmss/assets/128888356/be2b1924-9893-46a5-b97a-da7503e5bdc0)
![image](https://github.com/kamalmohan217/DevOps-Project-cicd-Azure-vmss/assets/128888356/aa33af5b-d3e7-4ed6-a6f4-c277fbd18543)
<br><br/>
Finally Application has been accessed as shown in the screenshot attached below.
![image](https://github.com/kamalmohan217/DevOps-Project-cicd-Azure-vmss/assets/128888356/9313127a-f158-4c00-97b1-635d5c9bdb4b)
![image](https://github.com/kamalmohan217/DevOps-Project-cicd-Azure-vmss/assets/128888356/040ee247-7d10-459e-b4b9-3393a3fad707)

<br><br/>
<br><br/>
<br><br/>
<br><br/>
<br><br/>
<br><br/>
<br><br/>
```
Source Code:-   https://github.com/kamalmohan217/aws-rds-java-azure-vmss.git
```
<br><br/>
<br><br/>
<br><br/>
<br><br/>
<br><br/>
<br><br/>
<br><br/>
```
Reference:-  https://ashok198510.hashnode.dev/cloud-native-two-tier-application-deployment-with-eks-tomcat-and-rds-in-aws
             https://github.com/Ashoksana/aws-rds-java.git
```
