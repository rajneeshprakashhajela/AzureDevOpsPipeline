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



