# Managing Azure Storage

## Objective

In this lab I learnt to create storage accounts for Azure blobs and Azure files. I learnt to configure and secure blob containers. I also learnt to use Storage Browser to configure and secure Azure file shares.

## Architecture diagram
![image](https://github.com/user-attachments/assets/b9186ea3-7706-4f0b-9720-c52a72c1a60f)
 

### Job Skills Learned

- Creating and configure a storage account.
- Creating and configure secure blob storage.
- Creating and configure secure Azure file storage.


### Tools Used

- Azure portal - https://portal.azure.com


## Steps
## Task 1: Create and configure a storage account.
In this task, you will create and configure a storage account. The storage account will use geo-redundant storage and will not have public access.
1.	Sign in to the Azure portal - https://portal.azure.com.
2.	Search for and select Storage accounts, and then click + Create.
3.	On the Basics tab of the Create a storage account blade, specify the following settings (leave others with their default values):
![image](https://github.com/user-attachments/assets/34272488-8a9b-4481-bacb-6ff9c8195adc)
 
1.	On the Advanced tab, use the informational icons to learn more about the choices. Take the defaults.
2.	On the Networking tab, review the available options, select Disable public access and use private access.
![image](https://github.com/user-attachments/assets/6b3925b0-07de-4ebc-92a4-384b2e128a6a)
 
3.	Review the Data protection tab. Notice 7 days is the default soft delete retention policy. Note you can enable blob versioning. Accept the defaults.
4.	Review the Encryption tab. Notice the additional security options. Accept the defaults.
5.	Select Review, wait for the validation process to complete, and then click Create.
6.	Once the storage account is deployed, select Go to resource.
![image](https://github.com/user-attachments/assets/7f9408fb-ff78-4384-9ba8-3c430eb3f44d)
 
7.	Review the Overview blade and the additional configurations that can be changed. These are global settings for the storage account. Notice the storage account can be used for Blob containers, File shares, Queues, and Tables.
8.	In the Security + networking section, select Networking. Notice public network access is disabled.
![image](https://github.com/user-attachments/assets/92845dd4-9961-4d21-8de9-5050523bb9b8)
 
o	Change the public access level to Enabled from selected virtual networks and IP addresses.
o	In the Firewall section, check the box for Add your client IP address.
![image](https://github.com/user-attachments/assets/18e4dc50-af9c-4946-b862-281ab73909c6)
 
o	Be sure to Save your changes.
9.	In the Data management section, view the Redundancy blade. Notice the information about your primary and secondary data center locations.
![image](https://github.com/user-attachments/assets/9457faa0-9a8e-4a7d-a6c8-ae086ecae23c)
 
10.	In the Data management section, select Lifecycle management, and then select Add a rule.
o	Name the rule Movetocool. Notice your options for limiting the scope of the rule.
o	On the Base blobs tab, if based blobs were last modified more than 30 days ago then move to cool storage. Notice your other choices.
o	Notice you can configure other conditions. Select Add when you are done exploring.
![image](https://github.com/user-attachments/assets/356bf191-41bb-45da-ae5d-046912a78d9f)
![image](https://github.com/user-attachments/assets/cb70eb40-a886-4c65-bdc6-44e7ae182e52)
 
 
## Task 2: Create and configure secure blob storage
In this task, you will create a blob container and upload an image. Blob containers are directory-like structures that store unstructured data.
Create a blob container and a time-based retention policy
1.	Continue in the Azure portal, working with your storage account.
2.	In the Data storage section, click Containers.
3.	Click + Container and Create a container with the following settings:
![image](https://github.com/user-attachments/assets/0ae448bf-8dff-4809-b7ee-7a7485d4c3da)
 
4.	On your container, scroll to the ellipsis (…) on the far right, select Access Policy.
5.	In the Immutable blob storage area, select Add policy.
![image](https://github.com/user-attachments/assets/b4e3171b-c6ca-46ef-b836-a1b645581400)
 
6.	Select Save.

Manage blob uploads
1.	Return to the containers page, select your data container and then click Upload.
2.	On the Upload blob blade, expand the Advanced section.
![image](https://github.com/user-attachments/assets/a65a3672-5813-4aa3-a212-8fe9c083fe05)
 
3.	Click Upload.
4.	Confirm you have a new folder, and your file was uploaded.
5.	Select your upload file and review the options including Download, Delete, Change tier, and Acquire lease.
![image](https://github.com/user-attachments/assets/365c4374-0239-40c5-a97b-c8c4af053dbc)
![image](https://github.com/user-attachments/assets/ebd74e06-20f7-42d4-894b-48d65dffaf1c)
![image](https://github.com/user-attachments/assets/99a37c3d-e04f-4354-9ed2-72bef11ddbe2)
    
6.	Copy the file URL and paste into a new Inprivate browsing window.
7.	You should be presented with an XML-formatted message stating ResourceNotFound or PublicAccessNotPermitted.
![image](https://github.com/user-attachments/assets/607705af-6084-403e-888d-d2569f6efa7b)
 
This is expected, since the container you created has the public access level set to Private (no anonymous access).


Configure limited access to the blob storage
1.	Select your uploaded file and then on the Generate SAS tab. You can also use the ellipsis (…) to the far right. Specify the following settings (leave others with their default values):
![image](https://github.com/user-attachments/assets/1ec1b3ff-e1d6-47fd-a4be-3c1519e7edbc)
 
2.	Click Generate SAS token and URL.
![image](https://github.com/user-attachments/assets/1ac8cdad-cf21-440a-bd1d-4d616f5bbfdb)
 
3.	Copy the Blob SAS URL entry to the clipboard.
4.	Open another InPrivate browser window and navigate to the Blob SAS URL you copied in the previous step.
![image](https://github.com/user-attachments/assets/c732f687-8e16-463a-a7ff-bd69a8171344)
 


## Task 3: Create and configure an Azure File storage
In this task, you will create and configure Azure File shares. You will use Storage Browser to manage the file share.
Create the file share and upload a file
1.	In the Azure portal, navigate back to your storage account, in the Data storage section, click File shares.
2.	Click + File share and on the Basics tab give the file share a name, share1.
3.	Notice the Access tier options. Keep the default Transaction optimized.
4.	Move to the Backup tab and ensure Enable backup is not checked. We are disabling backup to simplify the lab configuration.
5.	Click Review + create, and then Create. Wait for the file share to deploy.
![image](https://github.com/user-attachments/assets/3daa5ff0-fb9c-4c7f-8c08-62cc06188a2c)
 


Explore Storage Browser and upload a file
1.	Return to your storage account and select Storage browser. The Azure Storage Browser is a portal tool that lets you quickly view all the storage services under your account.
2.	Select File shares and verify your share1 directory is present.
![image](https://github.com/user-attachments/assets/7e4c7e40-c747-46d4-933b-fa31e787c9cc)
 
3.	Select your share1 directory and notice you can + Add directory. This lets you create a folder structure.
4.	Select Upload. Browse to a file of your choice, and then click Upload.
![image](https://github.com/user-attachments/assets/bea0db0a-eaca-49a5-bb53-c36361979246)
![image](https://github.com/user-attachments/assets/be40c712-6360-42ec-acec-3420a613b9da)
 
 


Restrict network access to the storage account
1.	In the portal, search for and select Virtual networks.
2.	Select + Create. Select your resource group. and give the virtual network a name, vnet1.
![image](https://github.com/user-attachments/assets/a65272f1-337a-42c6-aa97-f42315107a55)
 
3.	Take the defaults for other parameters, select Review + create, and then Create.
4.	Wait for the virtual network to deploy, and then select Go to resource.
5.	In the Settings section, select the Service endpoints blade.
o	Select Add.
o	In the Services drop-down select Microsoft.Storage.
o	In the Subnets drop-down check the Default subnet.
o	Click Add to save your changes.
![image](https://github.com/user-attachments/assets/f8e5ee24-123b-4402-9a52-cbe84cca3ba9)
 
7.	Return to your storage account.
8.	In the Security + networking section, select the Networking blade.
9.	Select add existing virtual network and select vnet1 and default subnet, select Add.
![image](https://github.com/user-attachments/assets/edb04165-d23b-48d8-961d-0197ea60a784)
 
10.	In the Firewall section, Delete your machine IP address. Allowed traffic should only come from the virtual network.
11.	Be sure to Save your changes.
12.	Select the Storage browser and Refresh the page. Navigate to your file share or blob content.
![image](https://github.com/user-attachments/assets/38ea40d3-25cb-46c5-9e1d-5ee341b90684)
 

