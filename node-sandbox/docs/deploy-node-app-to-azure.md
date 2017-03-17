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

2. Set the deployment user for App Service. You will deploy code using these credentials later.
   
	```
	az appservice web deployment user set --user-name <username> --password <password>
	```

3. Create a new [resource group](../azure-resource-manager/resource-group-overview.md). For this node.js tutorial, you don't really need to know
what it is.

	```
	az group create --location "<location>" --name my-nodejs-app-group
	```

    To see what possible values you can use for `<location>`, use the `az appservice list-locations` CLI command.

3. Create a new "FREE" [App Service plan](../app-service/azure-web-sites-web-hosting-plans-in-depth-overview.md). For this node.js tutorial, just 
know that you won't be charged for web apps in this plan.

	```
	az appservice plan create --name my-nodejs-appservice-plan --resource-group my-nodejs-app-group --sku FREE
	```

4. Create a new web app with a unique name in `<app_name>`.

	```
	az appservice web create --name <app_name> --resource-group my-nodejs-app-group --plan my-nodejs-appservice-plan
	```

5. Configure local Git deployment for your new web app with the following command:

	```
	az appservice web source-control config-local-git --name <app_name> --resource-group my-nodejs-app-group
	```

    You will get a JSON output like this, which means that the remote Git repository is configured:

	```
	{
		"url": "https://<deployment_user>@<app_name>.scm.azurewebsites.net/<app_name>.git"
	}
	```

6. Add the URL in the JSON as a Git remote for your local repository (called `azure` for simplicity).

	```
	git remote add azure https://<deployment_user>@<app_name>.scm.azurewebsites.net/<app_name>.git
	```
   
7. Deploy your sample code to the `azure` Git remote. When prompted, use the deployment credentials you configured earlier.

	```
	git push azure master
	```
   
    The Express generator already provides a .gitignore file, so your `git push` doesn't consume bandwidth trying to upload the node_modules/ directory.

9. Launch your live Node app hosted in Azure.
   
	```
	az appservice web browse --name <app_name> --resource-group my-nodejs-app-group
	```
   
    You should now see your Node.js web app running live in Azure App Service.
   
## Update your Node.js web app
To make updates to your Node.js web app running in App Service, just run `git add`, `git commit`, and `git push` like you did when you first deployed your web app.

## Next steps
If you use a popular Node.js framework, such as [Sails.js][SAILSJS] or [MEAN.js][MEANJS] to develop apps, you can deploy those to App Service. The following tutorials will show you how to work with a specific framework in App Service:

* [Deploy a Sails.js web app to Azure App Service]
* [Create a Node.js chat application with Socket.IO in Azure App Service]
* [How to use io.js with Azure App Service Web Apps]

