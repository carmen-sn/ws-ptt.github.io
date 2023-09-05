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
1. Add **Update Record** action within the **IF** flow logic.

    ![relative](images/ex5/GIF09.gif)

    The **Update Record** action should look this this:

    ![relative](images/ex5/09.png)

{:style="counter-reset:none"}
1.  Add **Update Record** action within the **ELSE IF** flow logic.

    The **Update Record** action should look this this:

    ![relative](images/ex5/10.png)
    
{:style="counter-reset:none"}
1.  **Test** the workflow. After reviewing the test results, click **Cancel** from the Test flow modal.

    ![relative](images/ex5/11.png)

    The flow is **waiting for approval**

    ![relative](images/ex5/12.png)

{:style="counter-reset:none"}
1.  From the **All** Navigator, search for **My Approvals**, select Self-Service **My Approvals**.

    ![relative](images/ex5/13.png)

    Remove the filter breadcrumbs by clicking at the **All**. 

    ![relative](images/ex5/14.png)

    You should see the list of approval requests on the platform, please sort by Created field. Click **Requested** to open the approval record. 

    ![relative](images/ex5/15.png)

{:style="counter-reset:none"}
1.  Change the state to **Approved** and click **Update** button. The record is now approved. 

    ![relative](images/ex5/16.png)

{:style="counter-reset:none"}
1.  Access **Flow Designer** from the **All** navigator

    ![relative](images/ex5/17.png)

    Click **New** and select **Action** to create an reusable action. 

    ![relative](images/ex5/18.png)

    Give the action a name.  Click **Submit**

    ![relative](images/ex5/19.png)

{:style="counter-reset:none"}
1.  Create 3 **Inputs** for the action

    ![relative](images/ex5/20.png)

{:style="counter-reset:none"}
1.  Add a **Script** step after the inputs. The script 

```markdown
outputs.attachmentid = new sn_doc.GenerateDocumentAPI().generateDocumentForTask(inputs.record_id, inputs.doc_template_id, inputs.file_name);  
```
    ![relative](images/ex5/GIF21.gif)

    The result should look like this: 

   ![relative](images/ex5/21.png)

{:style="counter-reset:none"}
1.  Click **Publish**

{:style="counter-reset:none"}
1.  Return to AES flow designer and add the Generate PDF action within the **IF** flow logic.

    ![relative](images/ex5/GIF22.gif)

    You flow should look like this

    ![relative](images/ex5/22.png)

{:style="counter-reset:none"}
1. **Activate** your workflow.





[Next Exercise 6](/pages/ex6.html){: .btn .btn-purple }