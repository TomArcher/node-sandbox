---
title: Deploying a Node.js app to Azure | Microsoft Docs
description: Deploy a Node.js app to Azure using the Yeoman Express generator
keywords: Azure Node, Azure Node API Reference, Azure SDK
author: tarcher
manager: douge
ms.assetid: 853DED2B-3DBE-4AFC-8C5C-84504F2DFFC2
ms.service: Azure
ms.devlang: node
ms.topic: reference
ms.technology: Azure
ms.date: 3/21/2016
---

# Deploying a Node.js app to Azure

This topic illustrates how to deploy your Node.js application to Azure App Service using the Azure CLI.

## Prerequisites

- [Azure CLI 2.0](https://docs.microsoft.com/cli/azure/install-az-cli2)
- Microsoft Azure account - If you don't have an account, you can [sign up for a free trial](http://go.microsoft.com/fwlink/?LinkId=623901) or [activate your Visual Studio subscriber benefits](http://go.microsoft.com/fwlink/?LinkId=623901).

## Steps to deploy a Node.js app to Azure

1. Open a command prompt or bash window, and change directories to the location of your Node app.

1. Set the deployment user for App Service. Modify the &lt;username> and &lt;password> placeholders, and remember these values as they are used later when you deploy your code.

	```
	az appservice web deployment user set --user-name <username> --password <password>
	```

1. Create a [resource group](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-overview), which you can think of as a *namespace*, or *directory*, for helping to organize Azure resources.

	```
	az group create -n ta-node-demo-rg -l westus
	```

	The -l flag indicates the location of the resource group. While in preview, the App Service on Linux support is only available in select regions, so if you aren't located in the Western US, and you want to check which other regions are available, run `az appservice list-locations --linux-workers-enabled` from the command line to view your datacenter options.

1. Create the [App Service plan](https://docs.microsoft.com/en-us/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview) that will manage creating and scaling the underlying VMs to which your app is deployed. Once again, specify any value that you'd like for the name flag, however, make sure that the `-g` flag references the name that you gave to the resource group above.

	```
	az appservice plan create -n ta-node-demo-plan -g ta-node-demo-rg --is-linux
	```

	The `--is-linux flag` is key, since that is what indicates that you want Linux-based VMs. Without it, the CLI will provision Windows-based VMs.

1. Create the App Service web app, which represents your Node app that will be running within the plan and resource group just created. You can roughly think of a web app as being synonymous with a process or container, and the plan as being the VM/container host that they're running on.

	```
	az appservice web create -n ta-node-demo-app -p ta-node-demo-plan -g ta-node-demo-rg
	```

1. Create a new web app.

	```
	az appservice web create -n ta-node-demo -g ta-node-demo-rg -p ta-node-demo-plan
	```

1. Configure local Git deployment for your new web app with the following command.
 
	```
	az appservice web source-control config-local-git -n ta-node-demo -g ta-node-demo-rg
	```

1. Initialize Git in the app directory.

	```
	git init
	```

1. Using the URL returned from the previous step, add the remote endpoint. Replace the &lt;username> and &lt;password> placeholders with the appropriate values.

	```
	git remote add azure https://<username>:<password>@ta-node-demo.scm.azurewebsites.net/ta-node-demo.git
	```

1. Deploy your app.

	```
	git push azure master
	```

1. Launch the app to view the container that was just deployed, which will be available at an `*.azurewebsites.net` URL.

	```
	az appservice web browse -n ta-node-demo-app -g ta-node-demo-rg
	```

    You should now see your Node.js web app running live in Azure App Service.
   
>[!div class="step-by-step"]
[**Updating a Node.js app in Azure** &rarr;](get-started-updates.md)
