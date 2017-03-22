---
title: Configure the Node.js environment for Azure | Microsoft Docs
description: Install Node.js and the Azure CLI for your platform, and log in to your Azure account
keywords: Azure Node, Azure Node API Reference, Azure SDK
author: tarcher
manager: douge
ms.assetid: F8CD4D61-6D97-4F13-9952-EDDA82504318
ms.service: Azure
ms.devlang: node
ms.topic: reference
ms.technology: Azure
ms.date: 3/21/2016
---

# Configure the Node.js environment for Azure

The following steps guide you through configuring your environment to create and deploy Node.js apps to Azure:  

1. Get an Azure account. If you don't already have an Azure account, you can [sign up for a free trial](https://azure.microsoft.com/pricing/free-trial/?WT.mc_id=A261C142F) or [activate your Visual Studio subscriber benefits](https://azure.microsoft.com/pricing/member-offers/msdn-benefits-details/?WT.mc_id=A261C142F).

1. Install [Node.js](https://nodejs.org).

1. [Install the Azure CLI 2.0](https://docs.microsoft.com/en-us/cli/azure/install-az-cli2) for your platform. You'll use the CLI to create the Azure resources your app will need to run.

1. Open a command prompt or bash window.

1. Log in to Azure. Follow the prompt to log in with a Microsoft account that has your Azure subscription.

	```bash
	az login
	```   

	Once logged in successfully, you'll see a listing of Azure subscriptions associated with the Microsoft account you used.

1. The following command displays the details of the default Azure subscription.

	```bash
	az account show
	```   

	If the CLI is set up correctly, you'll see output like this from `az account list`:
	```json
	{
	  "environmentName": "AzureCloud",
	  "id": "ac6c882c-52b3-4dfb-99d3-bc76026cb6da",
	  "isDefault": true,
	  "name": "Visual Studio Enterprise",
	  "state": "Enabled",
	  "tenantId": "6c3b4f5c-a18b-455c-87b0-d9d26521a78c",
	  "user": {
	    "name": "frank@frabrikam.com",
	    "type": "user"
	  }
	}
	```

>[!div class="step-by-step"]
[**Create a Node app** &rarr;](get-started-create-node-app.md)
