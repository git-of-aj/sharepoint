- [Differences between SharePoint Server 2016 and 2019](https://support.microsoft.com/en-us/office/differences-between-sharepoint-server-2016-and-2019-ba84c8a3-3ce2-4252-926e-c67654ceb4a3)
- [More difference jn Editions](https://learn.microsoft.com/en-us/answers/questions/129299/feature-differences-between-sharepoint-server-2019)
- [sharepoint docs](https://learn.microsoft.com/en-us/sharepoint/getting-started)
- **SKillable labs**:
1. [55355A – SharePoint 2016 Administrator](https://koenig-solutions.learnondemand.net/Course/33976)
2. [55298A Introduction to SharePoint 2019](https://koenig-solutions.learnondemand.net/Course/24869)

## Intro 
[COmpany's sharepoint](https://koenigsolutionsltd.sharepoint.com/_layouts/15/sharepoint.aspx)
![image](https://github.com/user-attachments/assets/f29f0b85-2af1-4cdf-888b-bc1cce7d2962)
- [explain here](https://support.nhs.net/knowledge-base/sharepoint-best-practice-guidance-site-structure/)

- **Example of features**:
### Example: Project Management for a New Product Launch

**Scenario**: A company is launching a new product and needs to coordinate efforts across multiple departments.

1. **Collaboration**: Team members from marketing, R&D, and sales use a dedicated SharePoint site to co-author project plans, share updates, and discuss tasks using integrated discussion boards and document libraries.
> sharepoint => `+ create site => Team Site`

3. **Enterprise Content Management (ECM)**: All project-related documents, such as research reports, marketing materials, and legal agreements, are stored in a structured manner with metadata for easy access and compliance.

4. **Web Content Management**: A public-facing site is created to promote the new product, featuring blog posts, videos, and product information, which marketing can update easily without needing IT support.
> sharepoint => `+ create site => Communication site`

6. **Social Computing**: Employees can share insights and feedback about the product launch on a dedicated community page, fostering engagement and collaboration across departments.

7. **Search**: Team members utilize SharePoint’s powerful search functionality to quickly locate documents, relevant discussions, and expert contacts related to the product launch.

8. **Business Intelligence (BI)**: The finance team creates dashboards in SharePoint that visualize sales forecasts, budget reports, and KPIs related to the product launch, enabling real-time data-driven decision-making.
> PowerBI Integration in sharepoint 

10. **Composites**: Custom workflows are built to automate approvals for marketing materials and budget expenditures, streamlining processes and ensuring accountability.

11. **Hybrid**: Sensitive product development documents are kept on-premises for security, while marketing materials and collaboration tools are hosted in SharePoint Online to facilitate remote work.

12. **Mobile Experience**: Sales representatives access the SharePoint mobile app to view the latest product information and marketing materials, allowing them to respond to customer inquiries while in the field.

### Summary:
In this scenario, SharePoint 2016 enables effective collaboration and management of resources across various functionalities, ensuring a successful and well-coordinated product launch.
## Logical archi
- Service applications are different SharePoint features which you can configure and share among different web applications. There are lot of built-in service applications which you can configure and benefit from.
Applications - if you are referring to custom applications, are the one you can develop using Browser, SharePoint Designer or Visual Studio to introduce new functionality into your solution.
> A Web application is composed of an Internet Information Services (IIS) Web site that acts as a logical unit for the site collections that you create. Before you can create a site collection, you must first create a Web application.
Each Web application is represented by a different IIS Web site with a unique or shared application pool. You can assign each Web application a unique domain name, which helps to prevent cross-site scripting attacks.
- The SharePoint config database is used by central administration to help manage all of your web applications, site collections, service applications, what's server and services are on the farm etc. The content databases are used to store the content from any web application you create such as site, documents,etc
## Information 
> Information architecture is about how you organize and label your content and how your visitors interact with the content to get work done. Modern SharePoint information architecture is also about how to ensure the right content gets to the right people and follows your organization’s content compliance regulations.

![](https://learn.microsoft.com/en-us/sharepoint/sharepointonline/media/roles.png) 

Information architecture covers six main elements that relate to way finding in SharePoint:

- Global navigational structure – Considered the top level of navigation across your SharePoint tenant and how you structure your sites so that users can find content including the home site of your intranet.
- Hub structure and organization – Hubs enable you to group together similar topics, tasks, and content.
- Local site and page navigational structure – How content is organized on each site and page so that users can further navigate or consume content effectively.
- Metadata architecture – Metadata impacts search and browsing structure as well as compliance and retention policies.
- Search experiences – How your users "consume" information architecture in addition to browsing.
- Personalized content experiences – How specific content is targeted to certain users and groups of users.

> Classic SharePoint architecture is typically built using a hierarchical system of site collections and subsites, with inherited navigation, permissions, and site designs. Once built, this structure can be inflexible and difficult to maintain. In the modern SharePoint experience, subsites aren't recommended.

![](https://learn.microsoft.com/en-us/sharepoint/sharepointonline/media/levels_of_nav.png)
- Global navigation for the entire collection of sites that comprise your intranet
- Hub navigation for groups of related sites
- Local navigation of an individual site
[Example screenshots from MS Docs](https://learn.microsoft.com/en-us/sharepoint/information-architecture-modern-experience)

## logical infra 
1. SharePoint farm runs on one or more 

servers and typically consists of several web 

applications and service applications. The farm 

configuration database stores the web 

application details and the service application 

associations within the farm, and there is only 

one farm configuration database per farm.

2. **Service applications (basically a code running over IIS)** . Service applications 

provide specific functionality to web 

applications within the farm or many sérvjce app => 1 web app 

`web app => app proxy => service app`

3. sites: just like folders in NSD (NETWORK SHARED DRIVE) : Create @ dept level / project put file web content, worflows etc 

4. site collection: When you create a new site collection, a special site known as a 

top-level site is created within the site collection. The top-level site is the highest site in the hierarchy 

of that particular site collection, and it has the shortest URL of all sites within that site collection. In 

addition, some site collection settings are accessible only from the top-level site settings page.

5. Content database. Each content database runs on SQL Server, and stores the content from one or 

more site collections. A content database can only be associated with one web application at a time.

site: 

> SharePoint refers to the information used to categorize and classify content as *metadata*

## Information architecture 
> Just like Grocery Store arranges
food 
1. Site columns. You can create site columns at the site level to store metadata as an additional column
- cant be inherited across site collection
2. term set
3. document set
4. content type

```sh
Demonstration: Examining SharePoint 2016 Central Administration 

In this demonstration, you will learn about the: 

• New service applications 

• Changes to the Search Service Application 

• Changes to web applications 

• New site templates 

Demonstration Steps 

1. Sign in to NYC-SP1 with the user name CONTOSO\Administrator, and the password Pa$$w0rd. 

2. Go to the Start screen, and then click SharePoint 2016 Management Shell. 

3. Type the following command, and then press Enter: 

psconfig.exe –help configdb 

4. Scroll to the top of the output and notice the new –localserverrole cmdlet and the six roles possible 

with the MinRole farm topology. 

5. Exit the SharePoint 2016 Management Shell. 

6. Go to the Central Administration site. 

7. On the Home page, click System Settings, and then on the System Settings page, under Servers, 

click Convert server role in this farm. 

8. Click the New Role drop-down list box, and notice that the same six roles are available. Do not 

change the current setting. 

 Note: The PowerShell WebFrontEnd is equivalent to the SharePoint 2016 Central 

Administration’s drop-down option Front End. 

9. Click Cancel. 

10. In a new browser tab, navigate to http://sharepoint.contoso.com. 

11. If prompted, sign in with administrator as the user name and Pa$$w0rd as the password. 

12. In the left navigation pane, click Documents. 

13. Create a new folder, and name the folder This…is…a {test} of the expanded & special characters.

```
## sharepoint online
- supports on prem
- many features of on prem are not supported 

## sharepoint hybrid 
- Hybrid deployments can use single sign-on, so that users only need to authenticate once by using an AD DS user account to gain 
access to both on-premises SharePoint farms and SharePoint Online
- cloud hybrid search to provide search results that encompass both on-premises SharePoint farms and 
SharePoint Online content for users of both environments.

> Things to remember: 

• Define your organization’s term sets before implementing SharePoint sites. This helps you create a 

better experience for your users in terms of data storage and retrieval. 

• Because SharePoint 2016 does not support single-server farms, you must plan for more hardware and 

decide on the exact roles that should run on the farm servers. 

• Implement new encryption, SMTP port settings, and IRM to provide a more secure environment. 

• To utilize the Excel Services fully, you need a combination of SharePoint 2016 and Microsoft SQL 

Server 2016. 

• SharePoint 2016 allows you to create a more seamless hybrid environment.
