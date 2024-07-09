<br>

<p align="center">
<img width="500" src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/5795419a-3012-4a57-b4b0-155c2dd93fc7" alt="Microsoft Active Directory Logo"/>
<br>
<br>
<br>



<h1> Create and Manage a SAS Key</h1>
<br>

In this exercise, you will **Generate a Shared Access Signature (SAS) Key** and an **Access Policy**.

1. First, you will **Create a Storage Account and a Container**, and then you will **Upload a Blob File to the Container**.

2. Next, you will **Generate a SAS Key**, and then you will **Test the Key for Access**.

3. Finally, you will **Generate an Access Policy**, and then you will **Test Access and Revocation**.

<br>


Azure provides storage accounts for storing data in the cloud as blobs, files, queues, and tables. You can grant access to data by using SAS keys and access policies.
<br>

<br>

<h2>1️⃣ Create a Storage Account and a Container</h2>
<br>

### ✔️ In this task, you will Create a Storage Account and a Container.
<br>

<br>

◻️ On the Azure portal menu, select **Create a resource** to display the Azure Marketplace.

<br>

◻️ In Search services and marketplace, search for and select ***Storage account***, and then select **Create**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-and-manage-a-SAS-key/assets/172988970/841a28ca-cf3d-41a6-8b4f-1cd1efec6c10" height="40%" width="40%" alt="9"/><br />
<br>

<br>

◻️ On the Create storage account blade, on the Basics page, in Resource group, select **corp-datalod42241754**, in Storage account name, enter ***stor42241754***, in Redundancy, select **Locally-redundant storage (LRS)**, and then select **Next : Advanced**.

<br>

◻️ On the Advanced page, review the default values, and then select **Next : Networking**.

<br>

◻️ On the Networking page, review the default values, and then select **Next : Data protection**.

<br>

◻️ On the Data protection page, review the default values, and then select **Review + create**

<br>

◻️ Review the configuration, and then select **Create**.

- Wait for the storage account to be created.
<br>

<br>

◻️ When you are presented with a **Your deployment is complete** message, select **Go to resource** to display the stor42241754 Storage account blade.

<br>

◻️ On the stor42241754 resource menu, in Data storage, select **Containers**.

<br>

◻️ On the Containers page, on the command bar, select **Container** to add a container.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-and-manage-a-SAS-key/assets/172988970/f99c7fed-6a1b-4331-980c-d6d02f837a2e" height="20%" width="20%" alt="9"/><br />
<br>

<br>

◻️ On the New container blade, in Name, enter ***images***, in Public access level, ensure that **Private (no anonymous access)** is selected, and then select **Create** to create the container.

<br>

◻️ On the Containers page, select **images**.

<br>

◻️ On the images page, on the command bar, select **Upload**.

<br>

◻️ On the Upload blob blade, in Files, select the folder icon.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-and-manage-a-SAS-key/assets/172988970/0633e153-5bc4-47e5-9366-2f026dd4e9f7" height="40%" width="40%" alt="9"/><br />
<br>

<br>

◻️ Select any image file on your computer—for example, **C:\Windows\blue-gray.JPG** ➔ and then select **Open**.

<br>

◻️ On the Upload blob blade, expand **Advanced**, in Block size, select **64 KB**, and then select **Upload**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-and-manage-a-SAS-key/assets/172988970/c258ee09-8eee-47c6-8597-325f4a5f278a" height="50%" width="50%" alt="9"/><br />
<br>

<br>

◻️ Close the **Upload blob** blade, and then verify that the uploaded blob file is now in the images container.

<br>


<br>
<br>

<h2>2️⃣ Generate a SAS Key</h2>
<br>

### ✔️ In this task, you will Create an SAS Key, and then you will Test the Key for Access.
<br>

<br>

◻️ If needed, on the Azure portal menu, select **All resources**, select the **stor42241754** storage account, and then select the **images** container.

<br>

◻️ On the images page, select the blob file that you uploaded.

<br>

◻️ On the Blob blade, select **Generate SAS**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-and-manage-a-SAS-key/assets/172988970/a7da6891-3630-4da5-b8da-62ab6b63a1c3" height="40%" width="40%" alt="9"/><br />
<br>

<br>

◻️ On the Generate SAS page, in Permissions, ensure that **Read** is selected, in Allowed protocols, ensure that **HTTPS only** is selected, and then select **Generate SAS token and URL**.

<br>

◻️ At the bottom of the page, in Blob SAS URL, select the **Copy to the clipboard** icon.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-and-manage-a-SAS-key/assets/172988970/50891231-bab3-4304-adb8-de2090f8bf7d" height="30%" width="30%" alt="9"/><br />
<br>

<br>

◻️ Close the Blob page.

<br>

◻️ Open a new browser window, and then go to the Blob SAS URL to display the contents of the blob file.

- The contents are displayed by using HTTPS and the SAS key. (If using C:\Windows\blue-gray.JPG, the image file displays a blue-gray background with 1920x1080 resolution).
<br>

<br>

◻️ Close the new browser window.
<br>


<br>
<br>


<h2>3️⃣ Create an Access Policy</h2>
<br>

### ✔️ In this task, you will Create an Access Policy, and then you will Test the Access Policy.
<br>

<br>

◻️ On the images resource menu, in Settings, select **Access policy**.

<br>

◻️ On the Access policy page, in Stored access policies, select **Add policy**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-and-manage-a-SAS-key/assets/172988970/21168b72-c255-425e-a062-126cfde854f9" height="20%" width="20%" alt="9"/><br />
<br>

<br>

◻️ On the Add policy page, in Identifier, enter ***BLOB-read-list***, and then in Permissions, select **Read** and **List**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-and-manage-a-SAS-key/assets/172988970/06633d98-653e-4596-9009-e0726daa29d3" height="70%" width="70%" alt="9"/><br />
<br>

<br>

◻️ In Start time, select the current date, and then ensure that the time value is set to ***12:00:00 AM***.

<br>

◻️ In Expiry time, select tomorrow’s date, ensure that the time value is set to ***12:00:00 AM***, and then select **OK**.

<br>

◻️ On the Access policy page, on the command bar, select **Save** to save the new access policy.

<br>

◻️ Close the **Access policy** page, to return to the stor42241754 Containers page.

<br>

◻️ On the stor42241754 resource menu, select **Storage browser (preview)**.

<br>

◻️ On the Storage browser (preview) page, select **Blob containers**, and then select **images**.

<br>

◻️ Right-click the blob file you uploaded, and then select **Generate SAS**.

<br>

◻️ On the Generate SAS blade, in Stored access policy, select **BLOB-read-list**, and then select **Generate SAS token and URL** to create the Blob SAS URL.

<br>

◻️ On the Generate SAS blade, in Blob SAS URL, select the **Copy** icon, and then close the Generate SAS blade.

<br>

◻️ Open a new browser window, and then go to the SAS URI you copied.

- The blob file is displayed by using the access policy.
<br>

<br>

◻️ Keep the browser window open for the next task.
<br>


<br>
<br>

<h2>4️⃣ Revoke an Access Policyy</h2>
<br>

### ✔️ In this task, you will Revoke an Access Policy, and then you will Verify Revocation.
<br>

<br>

◻️ Switch to the Azure portal, and then on the stor42241754 resource menu, select **Containers**.

<br>

◻️ Select the **images** container.

<br>

◻️ On the images resource menu, select **Access policy**.

<br>

◻️ On the Access policy page, in Stored access policies, select the ellipsis to the right of the BLOB-read-list policy, and then select **Delete**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-and-manage-a-SAS-key/assets/172988970/01b9a9e2-62f9-4a68-b9ea-4aadc33bdc89" height="90%" width="90%" alt="9"/><br />
<br>

<br>

◻️ On the Access policy page, on the command bar, select **Save**.

<br>

◻️ Switch to the browser window that contains the blob file contents, and then refresh the page.

<br>

◻️ Review the error message to verify that the access policy has been successfully revoked.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-and-manage-a-SAS-key/assets/172988970/58b7c3d0-16eb-4299-98cf-98f7bc21ffc3" height="50%" width="50%" alt="9"/><br />
<br>

<br>

◻️ Close the browser window that contains the error message.




<br>
<br>
<br>

