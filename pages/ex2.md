---
title: Exercise 2 Build Forms 
layout: default
nav_order: 3
---

# Exercise 2: Building an eForm with Record Producer
{: .fs-9 .text-blue-100}

**Duration: 20 minutes**

## Introduction
{: .text-blue-100}

From last exercise, we have configured the form for back office use. In this section, using the Record Producer, we will create a more user friendly and graphical eForm for users to make WFA requests.  As you will experience, we will encorporate the eFrom into Service Portal and/or Employee Center easily via wizard guided configurations.  

## Create the Record Producer
{: .text-blue-100}
1.  Return to the AES **App Home** tab.  Click **+Add** next to the section Experience.

    ![relative](images/ex2/01.png)

{:style="counter-reset:none"}
1.  On the **_What type of experience do you want to add to your app?_** page, select **Record producer**. Click **Begin**.

    ![relative](images/ex2/02.png)

{:style="counter-reset:none"}
1.  On the **_Let's set up your record producter._** page, name the record producer <span style="color:teal"> **PTT WFA Requests** </span>, and for description, enter <span style="color:teal"> **Fill in this form to submit a Work From Anywhere (WFA) request.** </span>.  Click **Continue**.

    ![relative](images/ex2/03.png)

{:style="counter-reset:none"}
1. On the **_Success! You added a record producer_** page, click **Edit record producer** button. 

    ![relative](images/ex2/04.png)

{:style="counter-reset:none"}
1. Navigate the steps of the record producers in the order as shown on the left side bar menu.  The right sidebar provides information of each step.  __Optionally__, enter item details as <span style="color:teal">**Your request for WFH will be routed to the approver.  Once approved, a PDF attachment will be generated for download.** </span> and/or attach an icon. 

    ![relative](images/ex2/05.png)

{:style="counter-reset:none"}
1. From top right, cilck the **Save** button, then click the **Preview** button. Review the header of your eForm.  Close the Preview but clicking the **X** on the top right. 

    ![relative](images/ex2/06.png)

{:style="counter-reset:none"}
1. Click the **Continue to Destination** button on the bottom right of the Details page. 

{:style="counter-reset:none"}
1. On the **_Destination_** page, search and select <span style="color:teal">**WFA Requests**</span> as the Table for record submission. 

    ![relative](images/ex2/07.png)

{:style="counter-reset:none"}
1. Click the **Continue to Location** button on the bottom right of the Destination page. 

{:style="counter-reset:none"}
1. On the **_Location_** page, click **Browse Catalogs**, select **Service Catalog**, click the **>** arrow.  Click **Save selections** button. 

    ![relative](images/ex2/08.gif)

{:style="counter-reset:none"}
1.  On the **_Location_** page, click **Browse Categories**, select  **Can We Help You?**, click the **>** arrow.  Click **Save selections** button. 

    ![relative](images/ex2/09.gif)

    This is what location should look like:

    ![relative](images/ex2/10.png)

{:style="counter-reset:none"}
1.  Click **Continue to Questions** button.

{:style="counter-reset:none"}
1.  Click the **down arrow** on the **Insert new question** button, select **Two column container**.

    ![relative](images/ex2/11.png)

    Insert <span style="color:teal">**WFA Request**</span> as the Title, click **Submit**. 

    ![relative](images/ex2/12.png)

{:style="counter-reset:none"}
1.  Click the **+ Insert** button beneath WFA Request container. Select **Single column container**.

    ![relative](images/ex2/14.png)

    Insert <span style="color:teal">**Details**</span> as the Title, click **Submit**. 

    ![relative](images/ex2/15.png)
    
{:style="counter-reset:none"}
1.  This is what your questions layout should look like after you click on the **arrow** to expand the containers.

    ![relative](images/ex2/16.png)
    
{:style="counter-reset:none"}
1.  Within the WFA Request container, click **+ Insert** button, select **New question**. 

    ![relative](images/ex2/17.png)
    
{:style="counter-reset:none"}
1.  Fill out the question details as below:

    Name | Selection / Values
    -------------- | --------------
    Question type | **Choice**
    Question subtype | **Dropdown (fixed values)**
    Map to a specific field on the table | **Checked** 
    Table field | **Request type** 
    Question label |<span style="color:teal">**What party would you like to request Work from Anywhere (WFA) for?**</span>
    Mandatory | **Checked**

    Click **Continue to Choices** button.

    ![relative](images/ex2/18.png)
    
    From the Choices tab, in Settings, **Check** the **Include non choice**. In the Available Choices section, enter:

    Display name | Value
    -------------- | --------------
    **WFA for self** |  wfa_for_self
    **WFA for Region** | wfa_for_region

    Click **Continue to Default value button**. 

    ![relative](images/ex2/19.png)
    
    From the Default value tab, select **WFA for self** as the Default value.  Note the option to preview the question on the right sidebar, try out the preview.  Click **Insert question** button. 

    ![relative](images/ex2/20.png)

{:style="counter-reset:none"}
1.  Repeat inserting questions in the WFA Request container:

    Name | Selection / Values
    -------------- | --------------
    Question type | **Choice**
    Question subtype | **Record reference**
    Map to a specific field on the table | **Checked** 
    Table field | **Requestor** 
    Question label |<span style="color:teal">**Requestor**</span>
    Mandatory | **Read-only**
    Additional Details >> Source Table | **User \[sys_user]**

    ![relative](images/ex2/20a.png)

    Click **Continue to Additional details** button. Select <span style="color:teal">**User \[sys_user]**</span> as the **Source table**.  Click the **Insert question** button.
    
    ![relative](images/ex2/20c.png)


1. Repeat inserting questions in the WFA Request container, this time we are going to insert read-only information about the requestor.

    Name | Selection / Values
    -------------- | --------------
    Question type | **Choice**
    Question subtype | **Record reference**
    Question label |<span style="color:teal">**Requestor Department**</span>
    Mandatory | **Read-only**
    Additional Details >> Source Table | **User \[sys_user]**
    Auto-populate >> depends on | **Requestor** 
    Auto-populate >> field that contains the value | **Department**

    The steps looks like the follows:

    ![relative](images/ex2/GIF01.gif)

1. Repeat inserting read-only information about the requestor on the form

    Name | Selection / Values
    -------------- | --------------
    Question type | **Choice**
    Question subtype | **Record reference**
    Map to a specific field on the table | **Checked** 
    Table field | **Approver** 
    Question label |<span style="color:teal">**Approver**</span>
    Mandatory | **Read-only**
    Additional Details >> Source Table | **User \[sys_user]**
    Auto-populate >> depends on | **Requestor** 
    Auto-populate >> field that contains the value | **Manager**

    The steps looks like the follows:

    ![relative](images/ex2/GIF02.gif)

    Click **Insert Question** button. 

{:style="counter-reset:none"}
1.  Repeat inserting questions in the WFA Request container:

    Name | Selection / Values
    -------------- | --------------
    Question type | **Date / Time**
    Question subtype | **Date**
    Map to a specific field on the table | **Checked** 
    Table field | **Start date** 
    Question label |<span style="color:teal">**Please specify the start date of WFA**</span>
    Mandatory | **Checked**

    ![relative](images/ex2/21.png)

    The steps looks like the follows:

    ![relative](images/ex2/GIF03.gif)
    
{:style="counter-reset:none"}
1.  Repeat inserting questions in the WFA Request container:

    Name | Selection / Values
    -------------- | --------------
    Question type | **Date / Time**
    Question subtype | **Date**
    Map to a specific field on the table | **Checked** 
    Table field | **End date** 
    Question label |<span style="color:teal">**Please specify the end date of WFA**</span>
    Mandatory | **Checked**

    ![relative](images/ex2/22.png)
    
{:style="counter-reset:none"}
1.  Up to this point, this is what your Quetions look like:

    ![relative](images/ex2/23.png)
    
{:style="counter-reset:none"}
1.  Let's add questions in the **Details** container.  The details of the new question:

    Name | Selection / Values
    -------------- | --------------
    Question type | **Text**
    Question subtype | **Multi-line**
    Map to a specific field on the table | **Checked** 
    Table field | **Description** 
    Question label |<span style="color:teal">**Please provide a justification for your WFA request**</span>

    ![relative](images/ex2/24.png)

{:style="counter-reset:none"}
1.  Up to this point, this is what your Quetions look like:

    ![relative](images/ex2/24a.png)   

{:style="counter-reset:none"}
1.  Click the **Preivew** button to preview the record producer, it should look like this"

    ![relative](images/ex2/24b.png)

{:style="counter-reset:none"}
1.  Close the **Preview**, and click **Continue to Settings** button

{:style="counter-reset:none"}
1.  From Settings, Check **Hide 'Add to wishlist' button** and Check **Hide attachment button**.  Click **Continue to Access** button. 

    ![relative](images/ex2/30.png)
    
{:style="counter-reset:none"}
1.  From Access, select **Available for** as **Any User**.  Click **Continue to Review and Submit**. 

    ![relative](images/ex2/31.png)
    
{:style="counter-reset:none"}
1.  Click **Submit**

    ![relative](images/ex2/32.png)
    
    
## Optional: Display requestor info in the form
{: .text-blue-100}

{:style="counter-reset:1"}
1.  In AES, return to **App Home** tab, click open the **PTT WFA Requests** record producer.

    ![relative](images/ex2/50.png)
    
{:style="counter-reset:1"}
1.  From the menu, click **Questions**, then add a new question in the **WFA Request** container:

    Name | Selection / Values
    -------------- | --------------
    Question type | **Choice**
    Question subtype | **Record reference**
    Map to a specific field on the table | **Checked** 
    Table field | **Requestor** 
    Question label |<span style="color:teal">**Requestor**</span>
    Read-only | **Checked**

    This is what the question look like:

    ![relative](images/ex2/51.png)
    
{:style="counter-reset:1"}
1.  Click **Additional details** tab, select **User \[sys_user\]** as the Source table.  Click **Insert Question**.

    ![relative](images/ex2/52.png)
    
    Name | Selection / Values
    -------------- | --------------
    Question type | **Choice**
    Question subtype | **Record reference**
    Question label |<span style="color:teal">**Requestor Department**</span>
    Read-only | **Checked**

    ![relative](images/ex2/53.png)
    
    Click **Additional details** tab, select **User \[sys_user\]** as the Source table.  Click **Insert Question**.

    ![relative](images/ex2/54.png)
    
    Click **Auto-populate** tab, **select the question this depends on** as **Requestor \| sys_user]**, and **Select the filed that contains the value you want to set** as **Department**

    ![relative](images/ex2/55.png)

    Click **Insert Question**.
    
{:style="counter-reset:none"}
1.  The Questions should look similar to the below. Click **Save**.

    ![relative](images/ex2/56.png)

## Configure Requestor as Logged in User
{: .text-blue-100}

{:style="counter-reset:1"}
1.  Return to ServiceNow Platform home page, you can do so by visiting the base URL  in a new browser tab.  For example, **http://<span style="color:teal">\[replace_with_your_instance_ID\]</span>.service-now.com**

    From the **All** navigator, search for <span style="color:teal">**Studio**</span>, and select **Studio**.  This will launch the pro-coder Studio tool.  

    ![relative](images/ex2/40.png)
    
{:style="counter-reset:none"}
1.  From Select Application window, search for <span style="color:teal">**PTT**</span> and click on the Application **PTT**.

    ![relative](images/ex2/41.png)
    
{:style="counter-reset:none"}
1.  Note that the **Application Explore** on the left sidebar shows the entire structure of the PTT application you have created using **AES** low code tool.  In the **Service Catalog > Record Producers** section, click **PTT WFA Requests** to open the record producer we previosly created using AES. 

    ![relative](images/ex2/42.png)

{:style="counter-reset:none"}
1.  From the related list, select the C**atalog Client Scripts** tab. Click **New** to create a new client script.

    ![relative](images/ex2/43.png)

{:style="counter-reset:none"}
1.  From the Catalog Client Script form, enter the following info:

    Name | Selection / Values
    -------------- | --------------
    Name | <span style="color:teal">**Requestor is Me**</span>
    UI type | **All**
    Type | **onLoad** 
    Applies on a Catalog Item view | **Checked** 
    Applies on Target Record| **Checked**
    Script |<span style="color:teal">**g_form.setValue('requestor', g_user.userID);**</span>

    ![relative](images/ex2/44.png)

    Click the **Submit** button. 

{:style="counter-reset:none"}
1.  Close the **Studio** browser tab. 

[Next Exercise 3](/pages/ex3.html){: .btn .btn-purple }