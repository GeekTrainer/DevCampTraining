Module 05 - Hook into Apps for Office
=====================================

##Overview
In this lab, configure Apps for Office in Word and Outlook. The lab uses an existing application that can be found in the src folder.

##Objectives
- Learn to configure Microsoft Azure to support Apps for Office
- Understand how to create a Word task pane app
- Understand how to create an Outlook app

##Prerequisites
- Visual Studio 2013 for Windows 8
- You must have an Office 365 tenant and Microsoft Azure subscription to complete this lab.
- You must have completed the lab associated with Module 2.

##Exercises
The hands-on lab includes the following exercises:<br/>
1. <a href="#Exercise1">Configure a Word app</a><br/>
2. <a href="#Exercise2">Configure an Outlook app</a><br/>

<a name="Exercise1"></a>
##Exercise 1: Configure a Word app
In this exercise you will configure and run a Word app in a task pane.

###Task 1 - Create a Research References List
Follow these steps to create a Research References List to hold links to pages.

1. Log into SharePoint Online using your **Organizational Account**.
2. On the site where the **Research Projects** list was created by the previous lab, create a new **Links** list named **Research References**.
3. After the list is created, add a new column to the list named **Project** as a **Single line of text**.

###Task 2 - Create Azure Active Directory App
Follow these steps to create the Azure Active Directory app.

1. Log into the [Azure Management Portal](https://manage.windowsazure.com) as an administrator.
2. Click **Active Directory**.
3. Click the Azure Active Directory associated with your subscription.
4. Click **Applications**.<br/>
     ![](img/01.png?raw=true "Figure 1")
5. Click **Add**.
6. Click **Add an application my organization is developing**.<br/>
     ![](img/02.png?raw=true "Figure 2")
7. Name the new app **WordResearchApp**.
8. Click the **arrow**.<br/>
     ![](img/03.png?raw=true "Figure 3")
9. Enter **https://localhost:44372/** in the **Sign-On URL** field.
10. Enter **https://localhost:44372/WordResearchApp** in the **App ID URI** field.
11. Click the **Checkmark**.<br/>
     ![](img/04.png?raw=true "Figure 4")

Now you have created a new Azure Active Directory app.

###Task 3 - Configure the Azure Active Directory App
Follow these steps to configure the Azure Active Directory app.

1. Click **Configure**.<br/>
     ![](img/05.png?raw=true "Figure 5")
2. Locate and copy the **Client ID**. **Save** the value for later.<br/>
     ![](img/06.png?raw=true "Figure 6")
3. In the **Keys** section, select **2 Years** for the duration.<br/>
     ![](img/07.png?raw=true "Figure 7")
4. Click the **Save** button.
     ![](img/08.png?raw=true "Figure 8")
5. After the settings save, copy the key. **Save** the value for later.<br/>
     ![](img/09.png?raw=true "Figure 9")
6. In the **Reply URL** section, add **https://localhost:44372/Home** and **https://localhost:44372/OAuth**.<br/>
     ![](img/10.png?raw=true "Figure 10")
7. Click the **Save** button.
     ![](img/08.png?raw=true "Figure 11")
8. In the **Permissions to Other Applications** section, select **Office 365 SharePoint Online**.
9. Grant **Create or Delete Items**, **Edit Items**, and **Read Items** permissions.<br/>
     ![](img/11.png?raw=true "Figure 12")
10. Click the **Save** button.
     ![](img/08.png?raw=true "Figure 13")

Now you have configured the Azure Active Directory app.

###Task 4 - Configure the MVC5 Web Application
Follow these steps to configure the MVC5 Web Application.

1. In Visual studio 2013, Open **Word.sln**, which is located in the **src** directory.
2. Expand the **WordResearchTrackerWeb** project.
3. Open the **web.config** file.
  1. **Replace** the **ida:Tenant** setting with the appropriate value for your environment.
  2. **Replace** the **ida:ClientID** setting with the value you saved earlier.
  3. **Replace** the **ida:AppKey** setting with the value you saved earlier.
  4. **Replace** the **ida:Password** setting with the same value you used in the **ida:AppKey** setting.
  5. **Replace** the **ida:Resource** setting with the appropriate value for your environment.
  6. **Replace** the **ida:SiteUrl** setting with the appropriate value for your environment.

Now the application is configured.

###Task 5 - Test the Application
Follow these steps to test the application.

1. Right click the **WordResearchTrackerWeb** project and select **Debug/Start New Instance**.
2. Right click the **WordResearchTracker** project and select **Debug/Start New Instance**.
3. When Word starts, log into Office 365 when prompted.
4. When the app appears, select a research project.
5. Select a research item.
6. Insert the item into the current Word document.

Now you have completed testing the application.

<a name="Exercise2"></a>
##Exercise 2: Configure an Outlook app
In this exercise you will configure and run an Outlook app in the mail client.

###Task 1 - Create Azure Active Directory App
Follow these steps to create the Azure Active Directory app.

1. Log into the [Azure Management Portal](https://manage.windowsazure.com) as an administrator.
2. Click **Active Directory**.
3. Click the Azure Active Directory associated with your subscription.
4. Click **Applications**.<br/>
     ![](img/01.png?raw=true "Figure 14")
5. Click **Add**.
6. Click **Add an application my organization is developing**.<br/>
     ![](img/02.png?raw=true "Figure 15")
7. Name the new app **OutlookResearchApp**.
8. Click the **arrow**.<br/>
     ![](img/12.png?raw=true "Figure 16")
9. Enter **https://localhost:44366/** in the **Sign-On URL** field.
10. Enter **https://localhost:44366/OutlookReasearchApp** in the **App ID URI** field.
11. Click the **Checkmark**.<br/>
     ![](img/13.png?raw=true "Figure 17")

Now you have created a new Azure Active Directory app.

###Task 2 - Configure the Azure Active Directory App
Follow these steps to configure the Azure Active Directory app.

1. Click **Configure**.<br/>
     ![](img/05.png?raw=true "Figure 18")
2. Locate and copy the **Client ID**. **Save** the value for later.<br/>
     ![](img/06.png?raw=true "Figure 19")
3. In the **Keys** section, select **2 Years** for the duration.<br/>
     ![](img/07.png?raw=true "Figure 20")
4. Click the **Save** button.
     ![](img/08.png?raw=true "Figure 21")
5. After the settings save, copy the key. **Save** the value for later.<br/>
     ![](img/09.png?raw=true "Figure 22")
6. In the **Reply URL** section, add **https://localhost:44366/Home** and **https://localhost:44366/OAuth**.<br/>
     ![](img/14.png?raw=true "Figure 23")
7. Click the **Save** button.
     ![](img/08.png?raw=true "Figure 24")
8. In the **Permissions to Other Applications** section, select **Office 365 SharePoint Online**.
9. Grant **Create or Delete Items**, **Edit Items**, and **Read Items** permissions.<br/>
     ![](img/11.png?raw=true "Figure 25")
10. Click the **Save** button.
     ![](img/08.png?raw=true "Figure 26")

Now you have configured the Azure Active Directory app.

###Task 3 - Configure the MVC5 Web Application
Follow these steps to configure the MVC5 Web Application.

1. In Visual studio 2013, Open **Outlook.sln**, which is located in the **src** directory.
2. Expand the **OutlookResearchTrackerWeb** project.
3. Open the **web.config** file.
  1. **Replace** the **ida:Tenant** setting with the appropriate value for your environment.
  2. **Replace** the **ida:ClientID** setting with the value you saved earlier.
  3. **Replace** the **ida:AppKey** setting with the value you saved earlier.
  4. **Replace** the **ida:Password** setting with the same value you used in the **ida:AppKey** setting.
  5. **Replace** the **ida:Resource** setting with the appropriate value for your environment.
  6. **Replace** the **ida:SiteUrl** setting with the appropriate value for your environment.

Now the application is configured.

###Task 4 - Test the Application
Follow these steps to test the application.

1. Right click the **OutlookResearchTrackerWeb** project and select **Debug/Start New Instance**.
2. Right click the **OutlookResearchTracker** project and select **Debug/Start New Instance**.
3. When prompted by the **Connect to Exchange E-mail Account** dialog, enter your credentials.
4. Click **Connect**.
5. When the **Outlook Web App** starts, you will need to locate an e-mail containing a hyperlink. (Note: In the current build, the hyperlink must be a literal value like http://www.microsoft.com).<br/>
     ![](img/16.png?raw=true "Figure 27")
6. Click **Research Tracker**.
7. If you receive an **App Error**, click **Retry**. A 401 error can occur during debugging if the app does not load fast enough.<br/>
     ![](img/17.png?raw=true "Figure 28")
8. If you receive a second error notification, click **Start**.<br/>
     ![](img/18.png?raw=true "Figure 28")
9. When the app starts, select a **Research Project**.
10. Select a **Discovered Link**.
11. Click **Add Link to project**.

Now you have completed testing the application.


##Summary
By completing this hands-on lab you learnt how to:
- Program OAuth in a Provider-Hosted app.
- Utilize the Cross-Domain library in a Provider-Hosted app.
