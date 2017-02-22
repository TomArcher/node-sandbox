# Azure NuGet packages for Node.js developers

This project provides a Node.js package that makes it easy to consume and manage
Microsoft Azure Services.

## Usage

This page lists all of the individual Azure Node.js packages in a single
place. To install a specific package, open a bash or command window on a machine with 
npm (Node Package Manager) installed, and execute the **Install command** listed next to the desired package
in the table.

## Individual Azure/Node.js NuGet packages

| **Azure Service** | **Install Command** |
| ----------------------------------------------------------------------------- | --------------------------- |
| [Gallery](http://azure.microsoft.com/en-us/marketplace/)                          | `npm install azure-gallery`       |
| [Graph](https://azure.microsoft.com/en-us/services/active-directory/)             | `npm install azure-graph`         |
| [Key Vault](http://azure.microsoft.com/en-us/services/key-vault/)                 | `npm install azure-keyvault`      |
| [Monitoring](https://msdn.microsoft.com/library/azure/dn306639.aspx)              | `npm install azure-monitoring`    |
| [Scheduler](http://azure.microsoft.com/en-us/services/scheduler/)                 | `npm install azure-scheduler`     |
| [Service Fabric](https://azure.microsoft.com/en-us/services/service-fabric/)      | `npm install azure-servicefabric` |
| [Service Bus](http://azure.microsoft.com/en-us/services/service-bus/)             | `npm install azure-sb`            |
| [Storage](http://azure.microsoft.com/en-us/services/storage/)                     | `npm install azure-storage`       |
| [Batch](https://azure.microsoft.com/en-us/services/batch/)                        | `npm install azure-batch`         |
| **Azure Resource Management (ARM)**                                                                                         |
| [Authorization](https://azure.microsoft.com/en-us/documentation/articles/role-based-access-control-configure/) | `npm install azure-arm-authorization`    |
| [Batch](https://azure.microsoft.com/en-us/services/batch/)                        | `npm install azure-arm-batch`     |
| [CDN](https://azure.microsoft.com/en-us/services/cdn/)                            | `npm install azure-arm-cdn`|
| [Commerce/Billing/Usage](https://azure.microsoft.com/en-us/documentation/articles/billing-usage-rate-card-overview/)                            | `npm install azure-arm-commerce`|
| [Compute](http://azure.microsoft.com/en-us/services/virtual-machines/)            | `npm install azure-arm-compute`|
| [Datalake Analytics](https://azure.microsoft.com/en-us/services/data-lake-analytics/) | `azure-arm-datalake-analytics`       |
| [Datalake Storage](https://azure.microsoft.com/en-us/services/data-lake-store/)   | `azure-arm-datalake-storage`       |
| [DNS](http://azure.microsoft.com/en-us/services/dns/)                             | `npm install azure-arm-dns`       |
| [DevTest Labs](https://azure.microsoft.com/en-us/services/devtest-lab/)           | `npm install azure-arm-devtestlabs`       |
| [EventHubs](https://azure.microsoft.com/en-us/services/event-hubs/)               | `azure-arm-eventhub`  |
| [HDInsight](http://azure.microsoft.com/en-us/services/hdinsight/)                 | `npm install azure-arm-hdinsight` |
| [HDInsightJobs](https://msdn.microsoft.com/en-us/library/azure/mt613023.aspx)     | `azure-arm-hdinsight-jobs` |
| [Insights](https://msdn.microsoft.com/en-us/library/azure/dn931943.aspx)          | `npm install azure-arm-insights`  |
| [IotHub](https://azure.microsoft.com/en-us/documentation/services/iot-hub/)       | `npm install azure-arm-iothub`  |
| [Key Vault](http://azure.microsoft.com/en-us/services/key-vault/)                 | `npm install azure-arm-keyvault`  |
| [Notification Hubs](https://azure.microsoft.com/en-us/documentation/services/notification-hubs/)                 | `azure-arm-notificationhubs`  |
| [PowerBi Embedded](https://azure.microsoft.com/en-us/services/power-bi-embedded/) | `azure-arm-powerbiembedded`  |
| [Redis Cache](https://azure.microsoft.com/en-us/services/cache/)                  | `npm install azure-arm-rediscache`   |
| [Resource Manager](https://azure.microsoft.com/en-us/documentation/articles/resource-group-overview/)    | `npm install azure-arm-resource`  |
| [ServerManagement](https://azure.microsoft.com/en-us/documentation/articles/resource-group-overview/)    | `azure-arm-servermanagement`  |
| [Servicebus](https://msdn.microsoft.com/en-us/library/mt639375.aspx)    | `azure-arm-sb`  |
| [Storage](http://azure.microsoft.com/en-us/services/storage/)                     | `npm install azure-arm-storage`   |
| [Traffic Manager](http://azure.microsoft.com/en-us/services/traffic-manager/)     | `npm install azure-arm-trafficManager`|
| [Virtual Networks](http://azure.microsoft.com/en-us/services/virtual-network/)    | `npm install azure-arm-network`   |
| [WebApps (WebSites)](http://azure.microsoft.com/en-us/services/app-service/web/)  | `npm install azure-arm-website`   |
| **Azure Service Management (ASM)**                                                                                          |
| [Compute](http://azure.microsoft.com/en-us/services/virtual-machines/)            |  `npm install azure-asm-compute`  |
| [HDInsight](http://azure.microsoft.com/en-us/services/hdinsight/)                 | `npm install azure-asm-hdinsight` |
| [Service Bus](http://azure.microsoft.com/en-us/services/service-bus/)             | `npm install azure-asm-sb`        |
| [Service Manager](https://msdn.microsoft.com/en-us/library/azure/ee460799.aspx)   | `npm install azure-asm-mgmt`      |
| [Store](http://azure.microsoft.com/en-us/marketplace/)                            | `npm install azure-asm-store`     |
| [Scheduler](http://azure.microsoft.com/en-us/services/scheduler/)                 | `npm install azure-asm-scheduler` |
| [SQL Database](http://azure.microsoft.com/en-us/services/sql-database/)           | `npm install azure-asm-sql`       |
| [Storage](http://azure.microsoft.com/en-us/services/storage/)                     | `npm install azure-asm-storage`   |
| [Subscriptions](https://msdn.microsoft.com/en-us/library/azure/gg715315.aspx)     | `npm install azure-asm-subscription`|
| [Traffic Manager](http://azure.microsoft.com/en-us/services/traffic-manager/)     | `npm install azure-asm-trafficManager`  |
| [Virtual Networks](http://azure.microsoft.com/en-us/services/virtual-network/)    | `npm install azure-asm-network`   |
| [WebSites](http://azure.microsoft.com/en-us/services/app-service/web/)            | `npm install azure-asm-website`   |
| **Base Libraries**                                                                |                                   |
| Common Functionality (for ASM & ARM clients)                                      | `npm install azure-common`        |
| Common Functionality for ARM clients generated from Autorest (Generic)            | `npm install ms-rest`             |
| Common Functionality for ARM clients generated from Autorest (Azure)              | `npm install ms-rest-azure`       |
