---
title: Exercise 5 Build the Workflow
layout: default
nav_order: 6
---

# Exercise 5: Build the Workflow
{: .fs-9 .text-blue-100}

**Duration: 20 minutes**

## Approval Request Workflow
{: .text-blue-100}
1.  Visit the ServiceNow **Employee Center**, you can do so by visiting the base URL adding **/esc** to the end (i.e. **http://<span style="color:teal">\[replace_with_your_instance_ID\]</span>.service-now.com<span style="color:teal">/esc</span>**) in a new browser tab.  

{:style="counter-reset:none"}
1.  Return back to App Engine Studio **AES Home** tab.  Click **+ Add** next to ***Logic and Automation**

    ![relative](images/ex5/01.png)

{:style="counter-reset:none"}
1.  From **What do you want to add?** page, select **Flow**

    ![relative](images/ex5/02.png)

{:style="counter-reset:none"}
1.  From **How do you want to add an automated workflow to your app?** page, select **Build from Scratch**

    ![relative](images/ex5/03.png)

{:style="counter-reset:none"}
1.  Name the flow as **WFA Request Flow**, Description as **Sends Approval Request and Generates PDF Document**, select Run as **System user**.  Click **Continue**.

    ![relative](images/ex5/04.png)

{:style="counter-reset:none"}
1.  Click **Edit this flow**

{:style="counter-reset:none"}
1.  Add a **trigger** to the flow.

    ![relative](images/ex5/GIF05.gif)

    The trigger should look like this:

    ![relative](images/ex5/05.png)

{:style="counter-reset:none"}
1.  Add an **Ask for Approval** Action.  

    ![relative](images/ex5/GIF06.gif)

    The action should look this this:

    ![relative](images/ex5/06.png)

{:style="counter-reset:none"}
1.  Add the **If** Flow logic for the **Approved** Condition

    ![relative](images/ex5/GIF07.gif)

    The **IF** flow logic should look this this:

    ![relative](images/ex5/07.png)

{:style="counter-reset:none"}
1.  Add the **Else If** Flow logic for the **Rejected** Condition

    ![relative](images/ex5/GIF08.gif)

    The **Else IF** flow logic should look this this:

    ![relative](images/ex5/08.png)


{:style="counter-reset:none"}
1.  

    ![relative](images/ex5/.png)

{:style="counter-reset:none"}
1.  

    ![relative](images/ex5/.png)

{:style="counter-reset:none"}
1.  

    ![relative](images/ex5/.png)

{:style="counter-reset:none"}
1.  

    ![relative](images/ex5/.png)

{:style="counter-reset:none"}
1.  

    ![relative](images/ex5/.png)
