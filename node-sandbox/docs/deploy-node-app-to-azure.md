# Deploying a Node.js app to Azure App Service

This topic illustrates how to deploy your Node.js application to Azure App Service. 

Using Azure App Service, you can enables you to deploy , which is Azure's PaaS offering, and recently added two new capabilities which are relevant to Node.js developers:

Support for Linux-based VMs, which reduces incompatibilities for apps which are built using native Node modules, or other tools which might not support Windows and/or may behave differently.

Support for Docker-based deployments, which allow you to simply specify the name of your Docker image, and allow App Service to pull, deploy and scale the image automatically.

To get started, open up your terminal, and we'll use the new Azure CLI 2.0 to manage your Azure account and provision the necessary infrastructure to run the todo app. Once you've logged into your account from the CLI using the az login command (as mentioned in the pre-reqs), perform the following steps in order to provision the App Service instance and deploy the todo app container: