![Image](https://i.imgur.com/ew2fvrw.png)

# Understanding File Permissions
Once again, this tutorial will not make sense unless you have completed the prerequisite tutorials. We will be focusing on the shares and permissions of files within our Active Directory domain. 

## Environments and Technologies Used

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Connection (RDC)
- Active Directory Domain Services

## Operating Systems Used 

- Windows Server 2022
- Windows 10 Pro (22H2)

## Creating Network File Shares

![Image](https://i.imgur.com/gQYbw72.png)

On DC-1, we will create four differently named folders in the C:\ drive. The naming conventions do not significantly impact the permissions aspect of this tutorial, but it is helpful to name them according to the permissions we will be assigning for the sake of clarity and understanding. Open the folder **Properties** of each file share, navigate to **Sharing**, click **Share**, type "domain users" into the line, click **Add**, and then click **Share** and **Done**. Repeat the same process for the others, with the difference being that you will adjust the permission level of each Domain_Users to correspond to the file shares (e.g., read, read/write, or no access). no-access will be shared with "Domain Admins" rather than "Domain Users"; their permission level will be read/write.


## Creating a Security Group

![Image](https://i.imgur.com/3Ab8tjI.png)

Open Active Directory Users and Computers under Tools, expand your domain and right-click Users, New, Group, enter a name for the group (e.g. "Support"), click ok to create the group.

![Image](https://i.imgur.com/yNZgyqR.png)

Open **Active Directory Users and Computers**. Under **Tools**, expand your domain, right-click **Users**, and select **New** > **Group**. Enter a name for the group (e.g., "Support") and click **OK** to create the group. Once the group is created, you can now add users by double-clicking **SUPPORT**, selecting **Members**, adding one of your created users (e.g., gib.kega), clicking **Apply**, and then **OK**.

![Image](https://i.imgur.com/A9UfXqG.png)

Navigate to the **support folder**, then proceed to add the SUPPORT security group via the properties. Ensure that they have Read/Write permissions.

## Test

![Image](https://i.imgur.com/oI9CYbf.png)

To wrap this up, we will connect to the user assigned under support to test various file shares. Log in as "gib.kega" (your user) and open the file directory. Enter `\\dc-1` into the file path, and it will take you to the network folders. From here, you can observe the permissions in action when attempting to use **no-access** and **support**. **no-access** is self-explanatory, but **support** would not have allowed us access if we had not assigned the user to that specific security group. You can also jump back and forth to manipulate and observe the folders as you wish, but you should now have the fundamentals to experiment if you desire.

---

That will be all for this file permission tutorial. It's not the hardest concept to wrap one's head around; it just takes a bit of repetitive visual realization to get the hang of it. Thank you for your time
