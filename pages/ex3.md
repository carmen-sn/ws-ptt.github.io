---
title: Exercise 3 Test the Form 
layout: default
nav_order: 4
---

# Exercise 3: Testing the Record Producer Form
{: .fs-9 .text-blue-100}

**Duration: 20 minutes**

## Introduction
{: .text-blue-100}

In this section we will test the record produce form created in Exercise 2. We will create a new WFA request by submitting the WFA Request form.    

## Test the WFA Request Form
{: .text-blue-100}
1. In a new browser tab, visit your instance base URL.  For example,  **http://<span style="color:teal">\[replace_with_your_instance_ID\]</span>.service-now.com**.  

{:style="counter-reset:none"}
1. Click the **All** navigator tab and search **user admin**, select **Users** under User Administration. 

    ![relative](images/ex3/11.png)

    Search for **Billie Cowley**. 

    ![relative](images/ex3/12.png)

    Open Billie's user record.  Click the **Role** tab from the related list, click **Edit**. 
    
    ![relative](images/ex3/13.png)

    From Collections, search for **x_snc_ptt**, identify the user role as **x_snc_ptt.user**, add this role for Billie.  

    ![relative](images/ex3/14.png)

    This is what Billie's roles list looks like

    ![relative](images/ex3/15.png)

    Click **Update** button to complete updating Billie's record. 

{:style="counter-reset:none"}
1. Click the settings icon to configure the user list layout to show Billie's manager info.

   ![relative](images/ex3/20.png)

{:style="counter-reset:none"}
1. Select the Personalized list as shown below.  Click **OK**.

   ![relative](images/ex3/21.png)

{:style="counter-reset:none"}
1. Now that Billie's **manager** is shown, click **Krystle Stika**. 

   ![relative](images/ex3/22.png)

    Click the **Role** tab from the related list, click **Edit**. 
    
    ![relative](images/ex3/23.png)

    From Collections, search for **approver**, identify the user role as **approver_user**, add this role for Krystle.  

    ![relative](images/ex3/24.png)

    Click Update on Krystle's user record. 

    ![relative](images/ex3/25.png)

{:style="counter-reset:none"}
1. Click the top-right **user icon**, from the drop-down select **Impersonate user**.

   ![relative](images/ex3/08.png)

    Search for **Billie Cowley** and click the **Impersonate User** button. 

    ![relative](images/ex3/09.png)

{:style="counter-reset:none"}
1.  As Billie Cowley, visit the ServiceNow **Service Portal**, use the base URL adding **/sp** to the end.  For example, **http://<span style="color:teal">\[replace_with_your_instance_ID\]</span>.service-now.com<span style="color:teal">/sp</span>**.

{:style="counter-reset:none"}
1.  In the **How can we help?** search bar, search for <span style="color:teal">**wfa request**</span>. 

    ![relative](images/ex3/05.png)

{:style="counter-reset:none"}
1.  Click on the first returned **Request** record producer which is the **PTT WFA Request**.  Note that there are data fields that are automatically populated as we included one script line to update the Requestor as the logged in user, and the user's relevant info such as department and manager (approver) is shown respectively.

    ![relative](images/ex3/06.png)

{:style="counter-reset:none"}
1.  This opens a new PTT WFA Request form.  Fill in the form. Click **Submit**

    ![relative](images/ex3/07.png) 
    
{:style="counter-reset:none"}
1.  The new request is then submitted. 

    ![relative](images/ex3/07a.png)

{:style="counter-reset:none"}
1.  Go back to the base URL of the instance.  Click on the top-left Profile icon, from the drop-down select **End Impersonation**.  

    ![relative](images/ex3/16.png)


[Next Exercise 4](/pages/ex4.html){: .btn .btn-purple }