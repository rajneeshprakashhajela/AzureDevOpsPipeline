Azure DevOps

1) Azure DevOps - Pipleline with .net core (restore, build, test, publish) <br/>
2) Azure DevOps - Pipleline with .net core (restore, build, test, publish), SonarQube<br/>
3) Azure DevOps - Pipleline with .net core (restore, build, test, publish), SonarQube, Security tool<br/>
4) Azure DevOps - Pipleline with SQL Server DB (restore, build, test, publish), SonarQube, Security tool<br/>
5) Azure DevOps - Pipleline with SQL Server DB (restore, build, test, publish), SonarQube, Security tool, Security Vault<br/>
6) Azure DevOps - with Terraform<br/>
7) Azure DevOps with Kubernetes<br/>
8) Azure DevOps with Terraform & Kubernetes<br/>
<br/>

=================
Azure DevOps CICD Pipeline via YAML:<br/>

Build CI :<br/>
Restore Dependencies<br/>
Build application<br/>
Run unit tests<br/>
Upload packages<br/>

======================<br/>
task <br/>
 input<br/>
   Project: '**/webapp.csproj', '**/unittest.csproj', '**/unittest.csproj', Command: test<br/>
   argument: '--Configuration $(BuildConfiguration)'<br/>

======================<br/>
task <br/>
 input
   Project:  '**/unittest.csproj', <br/>
   Command: test<br/>
   argument: '--Configuration $(BuildConfiguration)'<br/>
======================<br/>
task  (Create a web app package)<br/>
 input<br/>
   publishwebprojects:True<br/>
   Command: Publish<br/>
   argument: '--Configuration $(BuildConfiguration)' --output $(build.articfactstagingdirectory)"<br/>
======================<br/>
task  (.zip)<br/>
 input<br/>
    PathtoPublish:'$(build.artifactstagingdirectory)'<br/>
================================<br/>
![image](https://user-images.githubusercontent.com/43515480/232720861-acb676cc-886c-4029-999e-bf62f2bd067a.png)
![image](https://user-images.githubusercontent.com/43515480/232720888-4fc743ce-797c-4689-a5e5-a40c38170da4.png)

![image](https://user-images.githubusercontent.com/43515480/232720725-17076258-2de3-4130-a0c7-1e130b8e3d27.png)





![image](https://user-images.githubusercontent.com/43515480/232722724-a023fc19-41b2-4321-af30-b819e71e1923.png)

![image](https://user-images.githubusercontent.com/43515480/232724090-2132ff46-ae33-45fc-bf7b-6879004e6415.png)
![image](https://user-images.githubusercontent.com/43515480/232724242-b1dfcc1e-05ea-4f00-aee1-dafcd6970119.png)

![image](https://user-images.githubusercontent.com/43515480/232724392-6eb2be6f-080d-46cf-ac03-93288e9031ac.png)
![image](https://user-images.githubusercontent.com/43515480/232724466-5552655f-87fe-4566-a548-6dba651c0aa8.png)
![image](https://user-images.githubusercontent.com/43515480/232724520-bfd57092-287c-4c7e-a430-a636007abb8b.png)

![image](https://user-images.githubusercontent.com/43515480/232724662-76471b3f-38e0-4fa0-8caa-5c7344d2b5aa.png)
![image](https://user-images.githubusercontent.com/43515480/232724697-1334dc4e-37d9-48f6-81c8-7ad5bd901ffd.png)
![image](https://user-images.githubusercontent.com/43515480/232724756-0d7924ed-7cfb-4421-92d1-13f0b9516507.png)
