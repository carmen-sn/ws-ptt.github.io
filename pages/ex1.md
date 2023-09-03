---
title: Exercise 1 Build Data Table
layout: default
nav_order: 2
---

# Exercise 1: Build the Data Model
{: .fs-9 .text-blue-100}

**Duration: 20 minutes**

## Introduction
{: .text-blue-100}

In the first section, we will create two tables. Our first table will be used to capture the Travel Requests coming in from employees, and our second table will be used to store all the major airports and cities that can be traveled to. We will assume that all Travel Requests will only be for air travel.

## Create the Scoped Application
{: .text-blue-100}
1.  Click **All**, then search and click <span style="color:teal">**App Engine Studio**</span> (AES)

    ![relative](/images/ex1/1openaes.png)

{:style="counter-reset:none"}
1.  Click <span style="color:teal">**Create app**</span> on the top right of the screen

    ![relative](/images/ex1/2createapp.png)

{:style="counter-reset:none"}
1.  On the Create App page, name the app <span style="color:teal"> **PTT**</span>, and for description, enter <span style="color:teal"> **This is a low code app to manage PTT WFA requests** </span>.  *Optional*, add a logo to your application. 

    ![relative](/images/ex1/3.png)

{:style="counter-reset:none"}
1.  Click **Continue**

{:style="counter-reset:none"}
1.  Leave the default roles as *admin* and *user*, and click **Continue**.  

    ![relative](/images/ex1/4.png)

{:style="counter-reset:none"}
1.  Click **Go to app dashboard**

    ![relative](/images/ex1/5.png)

{: .note-title .text-grey-dk-000}
> Note:
>
> What you’ve just done is create a scoped application. Scope uniquely identifies every application file, why is this important?
> -  Scope protects an application, its files, and its data from conflicts with other applications.
> -  Scope determines which parts of an application are available for use by other applications in ServiceNow.
> -  Scope allows developers to configure which parts of their application can be acted on by other applications.
> -  Scope prevents work done in the main ServiceNow browser window (not in Studio) from becoming part of an application’s files.
> -  Without Scope, it will be very difficult to govern new applications!
>

## Create the Work-from-Anywhere (WFA) Table
{: .text-blue-100}

We will now create a table to capture the WFA requests. 

1. Under **Data**, click **Add**  

    ![relative](/images/ex1/6.png)

{:style="counter-reset:none"}
1.  On the **_How do you want to add data to your app?_** page, click **Create a blank table**.  Click **Continue**.

    ![relative](/images/ex1/7.png)

{:style="counter-reset:none"}
1.  On the **_How do you want to create table page?_**  page, select **Create from an extensible table**.  Click **Continue**.

    ![relative](/images/ex1/8.png)

{:style="counter-reset:none"}
1.  On the next page, click **Table**, and select <span style="color:teal"> **Task** </span> under *Recommended Tables*.  Click **Continue**.

    ![relative](/images/ex1/9.png)
   
    ![relative](/images/ex1/10.png)

{: .note-title .text-grey-dk-000}
> Note: The task table is one of the core tables provided on the platform. Any table that extends task can take advantage of task-specific functionality such as SLAs and Approvals. This speeds up the overall process and ease of building logic and functionality.

{:style="counter-reset:none"}
1.  For **Table label**, enter <span style="color:teal">**WFA Requests** </span>. Table name should be auto-populated.  **Check** Auto number.  For Prefix, enter <span style="color:teal"> **WFAREQ** </span>.  Click **Continue**.

    ![relative](/images/ex1/11.png)

{:style="counter-reset:none"}
1.  Allow <span style="color:teal">**All**</span> access for **_admin_**, and <span style="color:teal">**Create, Read, Write**</span> access for **_user_**.  Click **Continue**.

    ![relative](/images/ex1/12.png)

{:style="counter-reset:none"}
1.  Click **Edit table**.  If presented with the **Welcome to Table builder** pop-up, read through the steps, then close it.

    ![relative](/images/ex1/13.png)  

    ![relative](/images/ex1/14.png)  

{:style="counter-reset:none"}
1.  You should now be on the *Table Builder* interface, in the *Spreadsheet view*.  To switch to the **_field_** view, click the 3 dots next to the **Data pill**, from the data views dropdown list select **Fields**.   Move your cursor over Column label table header, click the 3 dots on the right, select **Sort A to Z**. 

    ![relative](/images/ex1/14a.gif)  

{: .note-title .text-grey-dk-000}
> Note: There are several ways to add fields to a table, from the spreadsheet view, field view or form view.  From the **Field data view**, you can see that there are 69 data fields extended from the task table.  The most commonly used data fields, such as **Approval**, **Approval history**, task **State**, **Comments and Work notes** (audit log), **Additional comments** (log input) will be useful for the purpose of our application. Get familiar with the extended data fields. 

{:style="counter-reset:none"}
1.  Click **+ Add new field**. 

    ![relative](/images/ex1/14c.png)  

{:style="counter-reset:none"}
1.  Let's add the following list of data fields:

    Column label | Type
    -------------- | --------------
    Request type | **Choice**, Choice Type is **Dropdown with -- None --**, Choices Labels are **WFA for self**, **WFA for Region**, Default value is **WFA for self**
    Start date | Date
    End date | Date 
    Approval date | Date 

    ![relative](/images/ex1/14e.gif)  

    The added data fields should look similar to the following:

    ![relative](/images/ex1/14f.png)

    Request type data field's Choice configurations is as follows:

    ![relative](/images/ex1/14g.png)

1. Click **Save**. 
    
{:style="counter-reset:none"}
1.  To configure the eForm, click on the **Forms** pill

    ![relative](/images/ex1/15.png)  

{:style="counter-reset:none"}
1.  The current form layout is inherited from the **Task** table, we will only keep the fields relevant to us.  Remove the following fields from the form:
- Priority
- Configuration item
- Parent

    ![relative](/images/ex1/16.png)  

    Here is a clip to show the steps in action:

    ![relative](/images/ex1/17.gif)  

    The form should look like this

    ![relative](/images/ex1/18.png) 

{:style="counter-reset:none"}
1.  Click the **Save** button. 

{:style="counter-reset:none"}
1.  We will add the following list of data fields to the form:
- Start date
- End date
- Request type
- Approval date 

    From the **_Add form elements_** left menu, search for **Request type**, drag and drop the Request type data field to the form view. 

    ![relative](/images/ex1/19.png) 

    Here is a clip to show the steps in action:

    ![relative](/images/ex1/20.gif)  

    The form should look like this

    ![relative](/images/ex1/21.png) 

{:style="counter-reset:none"}
1.  Click the **Save** button.

{:style="counter-reset:none"}
1.  Let's update the **Assigned to** data field label to <span style="color:teal">**Approver**</span>.  Select **Assigned to** field in the form editor. From the **Properties"** tab of the field configurations, change **Label** from **Assigned to** to <span style="color:teal">**Approvers**</span>

   ![relative](/images/ex1/22.png) 

{:style="counter-reset:none"}
1.  Click the **Save** button.  Click **Preview** to preview the form. Close the **Preview - Form** tab.

   ![relative](/images/ex1/23.png) 

[Next Exercise 2](/pages/ex2.html){: .btn .btn-purple }