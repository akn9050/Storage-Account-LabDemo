# Exercise 1 - Create a storage account using Azure portal
Use the Azure portal to create a storage account
- Login into the <https://portal.azure.com> using your credentials.
- On the Azure portal menu or from the **Home** page, select **Create a resource**.
- Select **Storage** under **Azure Marketplace**.
- On the right side of that pane, select **Storage account**.<br/>
  
  <img src="images/str1.jpg"/><br/>
 
 Under **PROJECT DETAILS:**
- Select the Concierge Subscription from the **Subscription** drop-down list.
- Select the existing Resource Group **odl-demo-xxxx** from the drop-down list.
Under **INSTANCE DETAILS:**
1. Enter a **Storage account name**. The name will be used to generate the public URL used to access the data in the account. The name must be unique across all existing storage account names in Azure. Names must be 3 to 24 characters long and can contain only lowercase letters and numbers.

2. Select a **Location** same as **Resource Group** Location.

3. Select Standard for the **Performance** option. This decides the type of disk storage used to hold the data in the Storage account.

4. Select StorageV2 (general purpose v2) for the **Account kind**. This provides access to the latest features and pricing. In particular, Blob storage accounts have more options available with this account type. You need a mix of blobs and a queue, so the Blob storage option will not work. For this application, there would be no benefit to choosing a Storage (general purpose v1) account, since that would limit the features you could access and would be unlikely to reduce the cost of your expected workload.

5. Select Locally-redundant storage (LRS) for the **Replication** option. Data in Azure storage accounts are always replicated to ensure high availability - this option lets you choose how far away the replication occurs to match your durability requirements.

6. Set the **Access tier** to Hot. This setting is only used for Blob storage. The **Hot Access Tier** is ideal for frequently accessed data, and the **Cool Access Tier** is better for infrequently accessed data.

The following screenshot shows the completed settings for the **Basics** tab. Note that the resource group, subscription, and name will have different values.

![](https://github.com/Gvashi/Storage-Account-LabDemo/blob/master/Images/image%202.png)
      
# Configure the networking options

1. Click the **Next: Networking >** button to move to the **Networking** tab, or select the **Networking** tab at the top of the screen.
2. Set the **Connectivity** method option to Public endpoint (all networks). This option allows you to isolate the storage account on an Azure virtual network. We want to use public Internet access. Our content is public facing and you need to allow access from public clients.

![](https://github.com/Gvashi/Storage-Account-LabDemo/blob/master/Images/5-create-storage-account-network.png)

# Configure the advanced options 
1. Click the **Next: Advanced >** button to move to the **Advanced** tab, or select the **Advanced** tab at the top of the screen.

2. Set **Secure transfer required** to Enabled. The **Secure transfer required** setting controls whether **HTTP** can be used for the REST APIs used to access data in the Storage account. Setting this option to Enabled will force all clients to use SSL **(HTTPS)**. Most of the time you'll want to set this to Enabled as using HTTPS over the network is considered a best practice.

3. **Leave the Large** file shares option set to Disabled. Large file shares provides support up to a 100TiB, however this type of storage account can't convert to a Geo-redundant storage offering and upgrades are permanent.

4. Leave the **Blob Soft delete** option set to Disabled. Soft delete lets you recover your blob data in many cases where blobs or blob snapshots are deleted accidentally or overwritten.

5. Leave the **Data Lake Storage Gen2** option as Disabled. This is for big-data applications that aren't relevant to this module.

The following screenshot shows the completed settings for the **Advanced** tab.

![](https://github.com/Gvashi/Storage-Account-LabDemo/blob/master/Images/5-create-storage-account-advanced.png)

### Create

1. Click **Review + create** to review the settings. This will do a quick validation of your options to make sure all the required fields are selected. If there are issues, they'll be reported here. Once you've reviewed the settings, click **Create** to provision the storage account.

It will take a few minutes to deploy the account. While Azure is working on that, let's explore the APIs we'll use with this account.

### Verify

1. Select the **Storage accounts** link in the left sidebar.
2. Locate the new storage account in the list to verify that creation succeeded.
