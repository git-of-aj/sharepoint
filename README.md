- site security : https://blog.netwrix.com/2023/03/24/sharepoint-security/
- Permission inheritance means a site inherits permissions from the root site of the site collection, and a subsite inherits permissions from its parent site. Folders, lists, and documents inherit permissions from the site that contains them, and so on.

[MS Docs sharepoint security](https://learn.microsoft.com/en-us/sharepoint/security-for-sharepoint-server/security-hardening)

### **Physical Security Components** (Infrastructure and Servers)
1. **Secure the SharePoint Farm by**:
   - Deploying SharePoint on dedicated servers in physically secure data centers, with restricted access to prevent unauthorized physical access to the farm.
   - Enforcing strict control over server room access through biometrics, keycards, or other physical security measures.

2. **Secure SharePoint Servers by**:
   - Ensuring that all SharePoint servers (web front-end, application, and database servers) are hosted in a secure environment with proper access control policies.
   - Regularly updating and patching the operating systems and SharePoint components to protect against vulnerabilities.

3. **Secure Backup and Disaster Recovery by**:
   - Storing SharePoint backups in a physically secure off-site location or cloud storage with encryption (both at rest and in transit).
   - Implementing a robust disaster recovery plan with regular testing to ensure quick recovery of SharePoint services after a physical disaster (e.g., server failure, fire, or natural disaster).

---

### **Logical Security Components** (Access Control, Permissions, and Data Protection)
1. **Secure SharePoint Sites by**:
   - Enforcing strong permissions management at the site collection level using **SharePoint groups** and **role-based access** (e.g., Owners, Members, Visitors) and using inheritance to simplify permissions.
   - Restricting access to site collections by configuring **IP-based restrictions** or **VPN** to ensure users can only access SharePoint from trusted locations or devices.

2. **Secure Document Libraries and Lists by**:
   - Configuring security on document libraries and lists to restrict access to specific users or groups. Avoid item-level permissions unless absolutely necessary, as they can complicate management.
   - Implementing **Information Management Policies** to enforce document retention, audits, and usage restrictions (e.g., preventing documents from being downloaded or printed).

3. **Secure SharePoint Data by**:
   - Ensuring that all sensitive data is encrypted both **at rest** (using file system encryption or SharePoint encryption features) and **in transit** (using HTTPS/SSL to secure data in transit over the network).
   - Using **BitLocker** or other disk encryption tools on SharePoint servers to protect stored data from unauthorized access in case of hardware theft.

4. **Secure User Access by**:
   - Enforcing **Active Directory (AD) authentication** and applying **Group Policy** settings to control user access to SharePoint servers and sites.
   - Requiring **multi-factor authentication (MFA)** for administrators and sensitive accounts to prevent unauthorized logins using compromised credentials.
   - Regularly reviewing **Active Directory group memberships** to ensure that only the right individuals have access to SharePoint resources.

5. **Secure SharePoint Search by**:
   - Configuring search security trimming to ensure that users only see results they are authorized to access, based on their SharePoint permissions.
   - Regularly auditing and reviewing search configurations to ensure that sensitive data is not exposed through search results, particularly for highly classified or confidential documents.

6. **Secure SharePoint Web Applications by**:
   - Enforcing **SSL/TLS encryption** for all SharePoint web traffic to secure data transmission between clients and servers.
   - Implementing **Web Application Firewall (WAF)** or proxy security features to mitigate common web-based attacks, such as cross-site scripting (XSS) and SQL injection.
   - Configuring **SharePoint farm security settings** to disable unnecessary or legacy features (e.g., basic authentication) that may present security risks.

7. **Secure SharePoint Database by**:
   - Using **SQL Server encryption** (e.g., Transparent Data Encryption - TDE) to protect SharePoint content databases from unauthorized access.
   - Ensuring the SQL Server instance hosting SharePoint databases is configured with strong access controls, including limiting direct access to the database server and using **Windows Authentication**.

8. **Secure SharePoint Farm Administration by**:
   - Implementing the **least privilege** principle by restricting administrative access to SharePoint farm components (e.g., Central Admin) to only those who absolutely need it.
   - Using **role-based delegation** to assign administrative duties (e.g., site collection admin, farm admin) without giving full access to sensitive areas of the SharePoint environment.
[Configuring Web Part security](https://learn.microsoft.com/en-us/sharepoint/sites/manage-web-parts)
---

### **Security Monitoring and Auditing** (Logical Component)
1. **Monitor User Activity by**:
   - Enabling **SharePoint auditing** to track user actions such as document views, edits, and deletions. This provides visibility into who is accessing what data.
   - Integrating SharePoint with **SIEM** (Security Information and Event Management) tools to collect and analyze logs for suspicious activity and compliance reporting.

2. **Monitor SharePoint Health by**:
   - Using **SharePoint Health Analyzer** and **SQL Server Profiler** to monitor SharePoint and database server performance, availability, and any unusual activities.
   - Setting up regular **health checks and vulnerability assessments** to ensure security patches are applied promptly and the farm configuration remains secure.

3. **Manage Patch and Update Cycles by**:
   - Implementing a structured **patch management process** to apply security updates and patches regularly to both SharePoint and underlying infrastructure (Windows, SQL Server).
   - Testing patches in a non-production environment to ensure compatibility before deploying to the live farm.

---
- [configuring the User Profile Service Application](https://learn.microsoft.com/en-us/sharepoint/install/create-a-user-profile-service-application)
By securing both the **physical infrastructure** and **logical components** of your **SharePoint on-premises** environment, you can create a strong security posture that helps protect sensitive data, ensures compliance, and minimizes the risk of unauthorized access or data loss.
---
[create, add, delete users](https://services.dartmouth.edu/TDClient/1806/Portal/KB/ArticleDet?ID=67055)

Here are the methods to add users in **SharePoint 2016**:

1. Add Users via **Site Permissions** (Directly from Site)
2. Add Users to **SharePoint Groups**
3. Add Users from **Active Directory** (via Central Administration)
4. Add Users using **PowerShell**
5. Add Users through **SharePoint List**
6. Add **External Users** (External Sharing)
7. Add Users using **Active Directory Groups**
8. Add Users via **SharePoint API** (Client Object Model or REST)
9. Add Users through **Office 365 Admin Center** (in hybrid setups)
10. Add Users using **SharePoint Designer**

## Sharepoint Audience
- In SharePoint Server, an audience is a feature that allows you to target content to specific groups of users based on certain criteria. These criteria can be attributes from Active Directory (e.g., department, job title, or location), SharePoint group membership, or even custom criteria. Audiences help in customizing the content and improving user experience by delivering relevant information to the right users at the right time.
```
How to add an user to a SharePoint site? 
Applies to
SharePoint 2013
Prerequisites
An existing SharePoint site.
A SharePoint user.
Steps
step 1Open the SharePoint site to which you wish to add users.step 2Click on Site Actions (gear icon) and then select Site Settings.step 3Under the Users and Permissions category, click Site Permissions → Permissions → Grant Permissions.step 4In the given Invite people to field, enter the user's email address or username and select the appropriate user from the drop down menu that appears.step 5Choose the permission that should be granted to the user from Show Options, and click on Share.
The user will now be created with the specified permissions. 
```
## [Taxonomy best Practices](https://www.mrsharepoint.guru/sharepoint-taxonomy-guide-how-to-configure-and-design/)
## [Managed Metadata best practice](https://www.clearpeople.com/blog/sharepoint-metadata-and-managed-metadata-best-practices)
# [sharepoint](https://learn.microsoft.com/en-us/sharepoint/sharepoint-server)
## [youtube - install 2019](https://youtu.be/Sjl3ixS_724?si=gO8GM4zXTewsS7MW)
## 2019 install page - https://www.microsoft.com/en-in/download/details.aspx
## terms
- `Office Online Server`: delivers browser-based versions of Word, PowerPoint, Excel, and OneNote. A single Office Online Server farm can support users who access Office files through SharePoint Server, Exchange Server, shared folders, and web sites. [docs](https://learn.microsoft.com/en-us/officeonlineserver/office-online-server-overview)
- `cliconfg.exe` is a utility provided by Microsoft Windows for configuring the client settings for SQL Server. It allows users to set up and manage the network connections used by SQL Server client
- `SYSWOW64`: It's located under C:\Windows, and it contains the 32-bit file components and resources that the operating system needs. Inside the SysWOW64 folder, you will find the 32-bit resources that the operating system needs to work properly. There, you may also find 32-bit shared components required for 32-bit applications.
