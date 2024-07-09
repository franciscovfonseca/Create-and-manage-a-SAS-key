<br>

<p align="center">
<img width="500" src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/5795419a-3012-4a57-b4b0-155c2dd93fc7" alt="Microsoft Active Directory Logo"/>
<br>
<br>
<br>



<h1> Create and Manage a SAS Key</h1>
<br>

In this exercise, you will generate a shared access signature (SAS) key and an access policy.

1. First, you will create a storage account and a container, and then you will upload a blob file to the container.

2. Next, you will generate a SAS key, and then you will test the key for access.

3. Finally, you will generate an access policy, and then you will test access and revocation.

<br>


Azure provides storage accounts for storing data in the cloud as blobs, files, queues, and tables. You can grant access to data by using SAS keys and access policies.
<br>

<br>

<h2>1️⃣ Create a Storage Account and a Container</h2>
<br>

### ✔️ In this task, you will Create a Storage Account and a Container.
<br>

<br>

◻️ On the Azure portal menu, select Create a resource to display the Azure Marketplace.

◻️ In Search services and marketplace, search for and select Storage account, and then select Create.

The Create Storage account option

On the Create storage account blade, on the Basics page, in Resource group, select corp-datalod42241754, in Storage account name, enter stor42241754, in Redundancy, select Locally-redundant storage (LRS), and then select Next : Advanced.

On the Advanced page, review the default values, and then select Next : Networking.

On the Networking page, review the default values, and then select Next : Data protection.

On the Data protection page, review the default values, and then select Review + create

Review the configuration, and then select Create.

Wait for the storage account to be created.

When you are presented with a Your deployment is complete message, select Go to resource to display the stor42241754 Storage account blade.

On the stor42241754 resource menu, in Data storage, select Containers.

On the Containers page, on the command bar, select Container to add a container.

The Add a container option

On the New container blade, in Name, enter images, in Public access level, ensure that Private (no anonymous access) is selected, and then select Create to create the container.

On the Containers page, select images.

On the images page, on the command bar, select Upload.

On the Upload blob blade, in Files, select the folder icon.

The Upload blob Files folder icon

Select any image file on your computer—for example, C:\Windows\blue-gray.JPG—and then select Open.

On the Upload blob blade, expand Advanced, in Block size, select 64 KB, and then select Upload.

The Upload blob blade

Close the Upload blob blade, and then verify that the uploaded blob file is now in the images container.





◻️ On the Azure portal menu, select **Create a resource** to display the Azure Marketplace.

<br>

◻️ In Search services and marketplace, search for and select ***SQL Database***, and then select **Create**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-an-Azure-SQL-database-that-uses-Microsoft-Defender-for-SQL/assets/172988970/6a0e9266-0562-4f5c-ace2-1bfae77b1019" height="40%" width="40%" alt="9"/><br />
<br>

<br>

◻️ On the Create SQL Database blade, on the Basics page, in Resource group, select **corp-datalod42241754**, in Database name, enter ***AdventureworksLT***, and then in Server, select **Create new**.

<br>

◻️ On the New server blade, in Server name, enter sql42241754, in Authentication method, ensure that **Use SQL authentication** is selected, in Server admin login, enter ***AzureAdmin***, and then in Password and Confirm password, enter ***AzPwd!42241754!***.

<br>

◻️ Select **OK** to save the details of the new server.

<br>

◻️ On the Basics page, in Compute + storage, select **Configure database**.

<br>

◻️ On the Configure page, in the Services tier dropdown list, select **Standard**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-an-Azure-SQL-database-that-uses-Microsoft-Defender-for-SQL/assets/172988970/b1f09665-f783-405e-9803-750db58538a7" height="70%" width="70%" alt="9"/><br />
<br>

<br>

◻️ Ensure that the **DTUs** slider is set to **10 (S0)**, ensure that the **Data max size** slider is set to **250 GB**, and then select **Apply**.

<br>

◻️ On the Basics page, verify that Compute + storage is set to **Standard S0**, and then select **Next : Networking**.

<br>

◻️ On the Networking page, in Connectivity method, select **Public endpoint**, in Allow Azure services and resources to access this server, select **Yes**, in Add current client IP address, select Yes, and then select **Next : Security**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-an-Azure-SQL-database-that-uses-Microsoft-Defender-for-SQL/assets/172988970/a5ec6d60-7934-40f7-94a7-d06415502639" height="80%" width="80%" alt="9"/><br />
<br>

<br>

◻️ On the Security page, in Enable Microsoft Defender for SQL, ensure that **Not now** is selected, and then select **Next : Additional settings**.

- You will enable Microsoft Defender for SQL in an upcoming task in this lab.
<br>

<br>

◻️ On the Additional settings page, in Use existing data, select **Sample**.

<br>

◻️ Select Review + create, review the SQL database configuration, and then select **Create** to deploy the database.

- The deployment will take approximately 2–3 minutes to complete.
<br>

<br>

◻️ When you are presented with a **Your deployment is complete** message, select **Go to resource** to display the AdventureworksLT SQL database page.

<br>

◻️ On the AdventureworksLT resource menu, select **Query editor (preview)**.

<br>

◻️ On the Query editor (preview) page, in SQL server authentication, log in as ***AzureAdmin*** using ***AzPwd!42241754!*** as the password.

<br>

◻️ Expand **Tables** to see the list of tables in the sample database.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-an-Azure-SQL-database-that-uses-Microsoft-Defender-for-SQL/assets/172988970/dcf6f413-165d-405e-8181-168ba0b3a115" height="70%" width="70%" alt="9"/><br />
<br>

<br>

◻️ In Query 1, enter the following Transact-SQL (T-SQL) statement:


```commandline
SELECT * FROM SalesLT.Customer
```
<br>

<br>

◻️ Select **Run** to select all of the rows from the SalesLT.Customer table.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-an-Azure-SQL-database-that-uses-Microsoft-Defender-for-SQL/assets/172988970/fc056a80-7261-4bc5-8be7-62e716afd659" height="50%" width="50%" alt="9"/><br />
<br>

<br>

◻️ On the Results page, verify that the query returned Customer data.

<br>

◻️ On the Messages page, verify that the message **Affected rows: 847** displayed.

- This indicates the number of rows in the SalesLT.Customer table.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-an-Azure-SQL-database-that-uses-Microsoft-Defender-for-SQL/assets/172988970/952352c0-0a70-4f4c-925f-c3a608a574d8" height="30%" width="30%" alt="9"/><br />
<br>


<br>
<br>

<h2>2️⃣ Enable Microsoft Defender for SQL</h2>
<br>

### ✔️ In this task, you will Configure Microsoft Defender for SQL.
<br>

1. First, you will enable **Microsoft Defender for SQL** for the AdventureworksLT database.
2. Next, you will perform a **Vulnerability Scan**.
3. Finally, you will enable **Auditing** at the server level based on the recommendations from the vulnerability scan.
<br>

<br>

◻️ On the AdventureworksLT resource menu, in Security, select **Microsoft Defender for Cloud**.

<br>

◻️ If prompted that Your unsaved edits will be discarded, select **OK**.

- If the Getting Started page appears, close it.
<br>

<br>

◻️ Select **Enable Microsoft Defender for SQL**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-an-Azure-SQL-database-that-uses-Microsoft-Defender-for-SQL/assets/172988970/2250ddae-9983-4b01-b798-d6a59bdb6ad1" height="80%" width="80%" alt="9"/><br />
<br>

<br>

◻️ On the Microsoft Defender for Cloud page, in the lower-left corner, select **View additional findings in Vulnerability Assessment**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-an-Azure-SQL-database-that-uses-Microsoft-Defender-for-SQL/assets/172988970/b3fb8a90-46fa-4f1d-beac-2e843a74b201" height="60%" width="60%" alt="9"/><br />
<br>

<br>

◻️ On the Vulnerability Assessment page, on the command bar, select **Scan**.

- After the assessment scan is complete, you will see a list of recommendations, similar to those shown in the following screenshot:
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-an-Azure-SQL-database-that-uses-Microsoft-Defender-for-SQL/assets/172988970/d26e3057-4909-48b3-a32e-70ce97311a6a" height="100%" width="100%" alt="9"/><br />
<br>

<br>

◻️ In the SECURITY CHECK column, select **Auditing should be enabled at the server level**.

<br>

◻️ On the VA2061 - Auditing should be enabled at the server level page, in the lower-left corner, select **Click here to remediate**.

<br>

◻️ On the Auditing page:
- turn on the **Enable Azure SQL Auditing** toggle
- select the **Storage** check box
- in Subscription, select the challenge subscription
- and then in Storage account, select the existing storage account name that begins with **sqlva**
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-an-Azure-SQL-database-that-uses-Microsoft-Defender-for-SQL/assets/172988970/a2b6f8c2-cecc-4a4e-a53b-a341c453d1ff" height="80%" width="80%" alt="9"/><br />
<br>

- 💡 The ***auditing*** feature for Azure SQL Database records database and server-level events and writes them to an audit log that can be hosted in an Azure storage account, a Log Analytics workspace, or an event hub.
<br>

<br>

◻️ On the Auditing page, on the command bar, select **Save**, and then wait for the save operation to complete.

<br>

◻️ When the save operation is complete, close the **Auditing** page.

- If you see a notification that your unsaved edits will be discarded, if you saved the edits, and you received a notification that your edits were saved, you can safely select OK to ignore the message.
<br>

<br>

◻️ Close the **VA2061 - Auditing should be enabled at the server level** page.

<br>

◻️ On the Vulnerability Assessment page, on the command bar, select **Scan**.

- After the assessment scan is complete, you should see that the Auditing should be enabled at the server level security check has now been removed from the list of recommendations because you have remediated that rule.
<br>

<br>

◻️ Close the **Vulnerability Assessment** page.
<br>

<br>
<br>


<h2>3️⃣ Manage Security Recommendations in Microsoft Defender for SQL</h2>
<br>

### ✔️ In this task, you will Remediate Vulnerabilities that were identified by a vulnerability assessment scan.
### ✔️ Then you will Approve a Current Configuration as a Baseline so it no longer appears as a recommendation.
<br>

<br>

◻️ On the AdventureworksLT (sql42241754/AdventureworksLT) resource menu, in Security, select **Data Discovery & Classification**.

<br>

◻️ On the Data Discovery & Classification page, select **We have found 15 columns with classification recommendations**.

<br>

◻️ Select the **Select all** check box, and then select **Accept selected recommendations**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-an-Azure-SQL-database-that-uses-Microsoft-Defender-for-SQL/assets/172988970/ba46164e-16db-4581-adce-84b38d6dbb8c" height="80%" width="80%" alt="9"/><br />
<br>

<br>

◻️ On the command bar, select **Save**.

<br>

◻️ On the AdventureworksLT (sql42241754/AdventureworksLT) resource menu, in Security, select **Microsoft Defender for Cloud**.

- If the Getting Started page appears, close it.
<br>

<br>

◻️ On the Microsoft Defender for Cloud page, in the lower-left corner, select **View additional findings in Vulnerability Assessment**.

<br>

◻️ On the Vulnerability Assessment page, in the SECURITY CHECK column, select **Server-level firewall rules should be tracked and maintained at a strict minimum**.

<br>

◻️ At the bottom of the VA2065 - Server-level firewall rules should be tracked and maintained at a strict minimum page, select **Click here to remediate**.

<br>

◻️ On the Firewall settings page, in Allow Azure services and resources to access this server, select **No**.

<br>

◻️ In Rule name, to the right of the rule that begins with **Clientip-**, select the ellipsis (…), and then select **Delete**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Create-an-Azure-SQL-database-that-uses-Microsoft-Defender-for-SQL/assets/172988970/73059a5b-eef2-442f-8533-7574f5809572" height="80%" width="80%" alt="9"/><br />
<br>

<br>

◻️ On the command bar, select **Save**, and then in the Success message box, select **OK**.

<br>

◻️ Close the **Firewall settings** page.

<br>

◻️ Close the **VA2065 - Server-level firewall rules should be tracked and maintained at a strict minimum** page.

<br>

◻️ On the Vulnerability Assessment page, select **'dbo' user should not be used for normal service operation**.

<br>

◻️ On the command bar, select **Approve as Baseline**, and then select **Yes** to continue.

<br>

◻️ Close the **VA1143 - 'dbo' user should not be used for normal service operation** page.

<br>

◻️ On the Vulnerability Assessment page, on the command bar, select **Scan**, and then wait for the assessment scan to complete.

- The security checks that you remediated no longer appear as recommendations.
<br>

<br>

◻️ Close the **Vulnerability Assessment** page.

<br>

◻️ On the AdventureworksLT (sql42241754/AdventureworksLT) resource menu, select **Query editor (preview)**.

<br>

◻️ On the Query editor (preview) page, in SQL server authentication, log in as ***AzureAdmin*** using ***AzPwd!42241754!*** as the password.

- Access from your IP address should be blocked because of the firewall rule you deleted.

- If you are still able to connect, refresh the browser, if prompted, select Reload, and then try to log in again. It may take a few minutes to apply the firewall rule.
<br>

<br>

◻️ Close the **Query editor (preview)** page, and if prompted by a Your unsaved edits will be discarded message, select **OK**.




<br>
<br>
<br>
