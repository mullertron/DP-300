# Overview

There are two main Database Provisioning Models when you create a new SQL PaaS Database

+ vCore Provisioning Model
+ DTU Based Provisioning Model

Within these Purchasing Models you can also choose elastic Database

## vCore Provisioning Model
This purchasing model is where you choose the number of vCores and Memory that you want for a Database

The higher number of vCores and Memory, the higher the price will be.

The vCore Model is also split into 3 different Tiers

+ General Purpose
+ Hyperscale
+ Business Critical

### General Purpose
This Tier is for common workloads that do not need high Disk I/O performance, the disk latency on this Tier is roughly 5ms
If you require a lower disk latency you would need to change to business Critical

Within the General purpose Tier, you can choose up to 80 vCores for your Database and up to 415GB of memory

Note: This can be different depending on the Hardware configuration that you pick

There also is a maximum size of the Database as 4TB - this will also change depending on the Hardware configuration selected.

Note: The default Hardware configuration is Standard Series (GEN 5)

When you change the vCore size the maximum Database size changes as well. For example, with a GEN 5 hardware configuration the max vCores is 80, when this is set the max database size is 4096GB (4TB). If you drop the vCores down to 40 the max Database size will be 3072GB (3 TB)

The maximum size transaction log alloctade will also be set at the same time, this is usually between a quarter and a third of the max database size.

For example, if the maximum database size is 4TB (4096GB) the Log Space allocated would be 1TB, if the maximum database size is 3TB (4096GB) the Log Space allocated would be 1TB, maximum database size is 1TB (4096GB) the Log Space allocated would be 307.2GB


#### Serverless
Within the General Purpose Tier of the vCore purchasing Model, there is also a Serverless option.

This enables you to pause the Database and not get charged when the database has not been in use for a specified period of time. You are only billed on a per second of usage basis while the Database is not Paused. However, you will be billed for the Storage used all of the time

The option is useful if you do not have constant connectivity to the Database

You configure the auto-pause any time between 1 hour and 7 days. As soon as there has been inactivity going over the mimimum auto-pause setting the Database will then pause and you will not be charged for the Database during that time. 

One thing to note here is that using this option will mean that the application may be required to have some retry logic set up when the connections hit a paused database. The Database will come back online quickly, but this could impact the Application. It would always be recomended to test this option before using it in a production environment.



#### Checking the different Hardware

If you click on change configuration link within the Hardware configuration setting, you will then be shown with all of the different Hardware compute options available 





#### Checking the different settings with the Hardware
