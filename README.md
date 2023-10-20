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

We will return to the "support" folder later.
