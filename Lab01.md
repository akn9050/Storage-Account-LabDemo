# Introduction to Azure Portal

**Excercise 1: Sign Up for pre configured environment**<br/>

In this exercise, you will create a source environment.

1.**Navigate** to bitly link which was provided by instructor and register by providing all required information and **clicking** on **SUBMIT button**.<br/>
2.Once registration is accepted, you will be automatically redirected to the lab activation page. Now, it is advised to save a copy of the URL on the browser, which has the activation id. **Click** on the Launch **Lab button**.<br/>
3.You will see the environment details soon below.<br/>

Please ensure to take the values assigned to your deployment.<br/>

**Excercise 2: Log into your Azure Portal and Verify access to the Subscription**<br/>

In this exercise, you will log into the Azure Portal using your Azure credentials and you will verify the type of role you are assigned 
1.**Navigate** to https://portal.azure.com and login (from the previous step).<br/>

2.**Enter** the Username which was displayed in the previous window and **click** on **Next**.

3.In the Stay signed in? pop-up window, click No. Enter the Password and click on **Sign in**.

4.In the Welcome to **Microsoft Azure** pop-up window, click **Maybe Later**. Initialize the **Azure CLI**.

# Exercise 1 - Create a storage account using Azure portal
Use the Azure portal to create a storage account


- **Login** to [Azure portal](https://portal.azure.com) using the credentials provided in the environment details page. You will be having access to one resource group.</br>
- On the Azure portal menu or from the **Home** page, select **Create a resource**.
- Select **Storage account** under **Azure Marketplace**. <br/>
 
  <img src="images/str1.jpg"/><br/>
 
 Under **PROJECT DETAILS:**
- In the Subscription field, select the **subscription** in which to create the storage account
- In the **Resource group** field, select an existing resource group or select **Create new**, and enter a name for the new resource group.
1. Enter a **Storage account name**. The name will be used to generate the public URL used to access the data in the account. The name must be unique across all existing storage account names in Azure. Names must be 3 to 24 characters long and can contain only lowercase letters and numbers.

2. In the **Location** field, select a location for the storage account, or use the default location.

3. Select Standard for the **Performance** option. This decides the type of disk storage used to hold the data in the Storage account.

4. Select StorageV2 (general purpose v2) for the **Account kind**. This provides access to the latest features and pricing. In particular, Blob storage accounts have more options available with this account type. You need a mix of blobs and a queue, so the Blob storage option will not work. For this application, there would be no benefit to choosing a Storage (general purpose v1) account, since that would limit the features you could access and would be unlikely to reduce the cost of your expected workload.

5. Select Locally-redundant storage (LRS) for the **Replication** option. Data in Azure storage accounts are always replicated to ensure high availability - this option lets you choose how far away the replication occurs to match your durability requirements.

6. Set the **Access tier** to Hot. This setting is only used for Blob storage. The **Hot Access Tier** is ideal for frequently accessed data, and the **Cool Access Tier** is better for infrequently accessed data.

The following screenshot shows the completed settings for the **Basics** tab. Note that the resource group, subscription, and name will have different values.

<img src="images/str2.jpg"/><br/>

      
# Configure the networking options

1. Click the **Next: Networking >** button to move to the **Networking** tab, or select the **Networking** tab at the top of the screen.
2. Set the **Connectivity** method option to **Public endpoint (all networks)**. This option allows you to isolate the storage account on an Azure virtual network. We want to use public Internet access. Our content is public facing and you need to allow access from public clients.

<img src="images/str3.jpg"/><br/>

If you plan to use **Azure Data Lake Storage**, choose the **Advanced tab**, and then set Hierarchical namespace to **Enabled**.

### Create

1. Click **Review + create** to review the settings. This will do a quick validation of your options to make sure all the required fields are selected. If there are issues, they'll be reported here. Once you've reviewed the settings.

Click **Create** to provision the storage account.

It will take a few minutes to deploy the account.

# Exercise 2 - Create a Container and Upload file using Azure portal

To create a container in the Azure portal, follow these steps:

1. Navigate to your new created storage account in the Azure portal.
2. In the left menu for the storage account, scroll to the **Blob service** section, then select **Containers**.
3. Select the + **Container** button.
4. Type a name for your new container. The container name must be lowercase, must start with a letter or number, and can include only letters, numbers, and the dash (-) character. For more information about container and blob names, see Naming and referencing containers, blobs, and metadata.
5. Set the level of public access to the container. The default level is **Private (no anonymous access).**
6. Select **OK** to create the container.

<img src="images/str5.jpg"/><br/>

## Upload a block blob

Block blobs consist of blocks of data assembled to make a blob. Most scenarios using Blob storage deploy block blobs. Block blobs are ideal for storing text and binary data in the cloud, like files, images, and videos. This quickstart shows how to work with block blobs.

To upload a block blob to your new container in the Azure portal, follow these steps:

1. In the Azure portal, navigate to the container you created in the previous section.
2. Select the container to show a list of blobs it contains. Since this container is new, it won't yet contain any blobs.
3. Select the **Upload** button to open the upload blade.
4. Browse your local file system to find a file to upload as a block blob.

<img src="images/str7.jpg"/><br/>

5. Optionally, expand the advanced section to define other setting such as authentication type, access tier, or virtual folder path.
6. Select the **Upload** button to commit the upload.
7. Upload as many blobs as you like in this way. You'll see that the new blobs are now listed within the container.

## Download a block blob

You can download a block blob to display in the browser or save to your local file system. To download a block blob, follow these steps:

1. Navigate to the list of blobs that you uploaded in the previous section.
2. Right-click the blob you want to download, and select **Download.**

