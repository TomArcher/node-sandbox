# Deploying an existing Node.js app to Azure App Service

This topic illustrates how to deploy your Node.js application to Azure App Service using the Azure CLI.

## Prerequisites

- [Azure CLI 2.0](https://docs.microsoft.com/cli/azure/install-az-cli2)
- Microsoft Azure account - If you don't have an account, you can [sign up for a free trial](http://go.microsoft.com/fwlink/?LinkId=623901) or [activate your Visual Studio subscriber benefits](http://go.microsoft.com/fwlink/?LinkId=623901).

## Deploy your Node.js app to Azure

1. Open a command prompt or bash window, and change directories to the location of your Node project.

1. Log in to Azure.

	```
	az login
	```

	Follow the prompt to log in with a Microsoft account that has your Azure subscription.

1. Create a [resource group](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-overview.md), which you can think of as a *namespace*, or *directory*, for helping to organize Azure resources.

	```
	az group create -n nina-demo -l westus
	```

	The -l flag indicates the location of the resource group. While in preview, the App Service on Linux support is only available in select regions, so if you aren't located in the Western US, and you want to check which other regions are available, run `az appservice list-locations --linux-workers-enabled` from the command line to view your datacenter options.

1. Create the [App Service plan](https://docs.microsoft.com/en-us/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview.md) that will manage creating and scaling the underlying VMs to which your app is deployed. Once again, specify any value that you'd like for the name flag, however, make sure that the `-g` flag references the name that you gave to the resource group above.

	```
	az appservice plan create -n nina-demo-plan -g nina-demo --is-linux
	```

	The --is-linux flag is key, since that is what indicates that you want Linux-based VMs. Without it, the CLI will provision Windows-based VMs.

1. Create the App Service web app, which represents your Node app that will be running within the plan and resource group just created. You can roughly think of a web app as being synonymous with a process or container, and the plan as being the VM/container host that they're running on.

	```
	az appservice web create -n nina-demo-app -p nina-demo-plan -g nina-demo
	```

1. Configure the web app to use our Docker image, making sure to set the -c flag to the name of your DockerHub account/image name.

	```
	az appservice web config container update -n nina-demo-app -g nina-demo -c lostintangent/node
	```

1. Launch the app to view the container that was just deployed, which will be available at an *.azurewebsites.net URL.

	```
	az appservice web browse -n nina-demo-app -g nina-demo
	```

    You should now see your Node.js web app running live in Azure App Service.
   
## Update your Node.js web app
To make updates to your Node.js web app running in App Service, just run `git add`, `git commit`, and `git push` like you did when you first deployed your web app.

## Next steps
If you use a popular Node.js framework, such as [Sails.js][SAILSJS] or [MEAN.js][MEANJS] to develop apps, you can deploy those to App Service. The following tutorials will show you how to work with a specific framework in App Service:

* [Deploy a Sails.js web app to Azure App Service]
* [Create a Node.js chat application with Socket.IO in Azure App Service]
* [How to use io.js with Azure App Service Web Apps]

