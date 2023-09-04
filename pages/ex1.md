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
1. Let's hide the extended data fields before we add more data fields. Click **Filter options** button and select **Hide extended fields**.

    ![relative](/images/ex1/14b.png)  

    With the extended data fields hidden, it's easier to note our newly added data fields with a clean palette.

    ![relative](/images/ex1/14bb.png)  


{:style="counter-reset:none"}
1.  Let's add the following list of data fields:

    Column label | Type
    -------------- | --------------
    <span style="color:teal">Request type</span> | **Choice**, Choice Type is **Dropdown with -- None --**, Choices Labels are **WFA for self**, **WFA for Region**, Default value is **WFA for self**
    <span style="color:teal">Status</span> | **Choice**, Choice Type is **Dropdown with -- None --**, Choices Labels are **Waiting for Approval**, **Waiting for Signature**, **Completed**, **Rejected**, Default value is **Waiting for Approval**
    <span style="color:teal">Start date</span> | Date
    <span style="color:teal">End date</span> | Date 
    <span style="color:teal">Approval date</span> | Date 
    <span style="color:teal">Approver</span> | **Reference** to the **User \[sys_user]** table
    <span style="color:teal">Requestor</span> | **Reference** to the **User \[sys_user]** table

{:style="counter-reset:none"}
1.  Click **+ Add new field**. 

    ![relative](/images/ex1/14c.png)  
    
{:style="counter-reset:none"}
1.  See the Animated GIF below on how the <span style="color:teal">**Request type**</span> field is added:

    ![relative](/images/ex1/GIF01.gif)  

{:style="counter-reset:none"}
1.  See the Animated GIF below on how the <span style="color:teal">**Status**</span> field is added:

    ![relative](/images/ex1/GIF02.gif)  

{:style="counter-reset:none"}
1.  See the Animated GIF below on how the <span style="color:teal">**Start date**</span>, <span style="color:teal">**End date**</span>, <span style="color:teal">**Approval date**</span> fields are added:

    ![relative](/images/ex1/GIF03.gif)  

{:style="counter-reset:none"}
1.  See the Animated GIF below on how the <span style="color:teal">**Approver**</span>, <span style="color:teal">**Requestor**</span> **reference** type fields are added:

    ![relative](/images/ex1/GIF04.gif)  

{:style="counter-reset:none"}
1.  The added data fields should look similar to the following:

    ![relative](/images/ex1/14f.png)

    Example of <span style="color:teal">**Request type**</span> data field's Choice configurations is as follows:

    ![relative](/images/ex1/14g.png)

1. Click **Save**. 
    

## Create the Backoffice eForm 
{: .text-blue-100}

{:style="counter-reset:1"}
1.  To configure the backoffice eForm (i.e. to be used in an Agent Workspace), click on the **Forms** pill.  

    ![relative](/images/ex1/15.png)  

{:style="counter-reset:none"}
1.  The current form layout is inherited from the **Task** table, we will only keep the fields relevant to us.  Remove the following fields from the form:
- Priority
- Configuration item
- Parent
- Short description

    ![relative](/images/ex1/16.png)  

    Here is a clip to show the steps in action:

    ![relative](/images/ex1/GIF05.gif)  

    The form should look like this

    ![relative](/images/ex1/18.png) 

{:style="counter-reset:none"}
1.  Click the **Save** button. 

{:style="counter-reset:none"}
1.  We will add the following list of data fields to the form:
- Requestor
- Approver
- Request type
- Status
- Start date
- End date
- Approval date 

    From the **_Add form elements_** left menu, search for **Request type**, drag and drop the Request type data field to the form view. 

    ![relative](/images/ex1/19.png) 

    Here is a clip to show the steps in action:

    ![relative](/images/ex1/GIF06.gif)  

    The form should look like this

    ![relative](/images/ex1/21.png) 

{:style="counter-reset:none"}
1.  Click the **Save** button.

{:style="counter-reset:none"}
1.  Click **Preview** to preview the form. Close the **Preview - Form** tab.

   ![relative](/images/ex1/23.png) 

{:style="counter-reset:none"}
1.  Let's make a few data field read-only as they will only be changed by the workflow or process configurations.  The **read-only** data fields includes 
- Requestor
- Approver
- Approval date
- Assigned to

    Click on the **Requestor** data field, from the Properties sidebar, check **read-only**.

    ![relative](/images/ex1/24.png)

    See the Animated GIF below on how the <span style="color:teal">**read-only**</span> fields are configured:

    ![relative](/images/ex1/GIF07.gif) 

    Preview the form, it should be similar to the below:

    ![relative](/images/ex1/25.png)


Congratulations, you have completed Exercise 1 and now have a complete way to store the WFA requests from your employees.

[Next Exercise 2](/pages/ex2.html){: .btn .btn-purple }