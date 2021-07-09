---
lab:
    title: 'Explore Azure Security Center'
    module: 'Module 3 Lesson 2: Describe the capabilities of Microsoft security solutions: Describe security management capabilities of Azure'
---


# Lab: Explore Azure Security Center 

## Lab scenario
In this lab, you will explore Azure Security Center and learn how Azure Secure Score can be used to improve your organization's security posture.

  

**Estimated Time**: 10-15 minutes

#### Task 1: In this task you will take a brief tour of Azure Security Center.
1.	Open Microsoft Edge. In the address bar enter **portal.azure.com**.

1. Sign in with your admin credentials.
    
    1. In the Sign in window enter **odl_user_XXXXXX@cloudlabsai.com** (where XXXXXX is your unique ID provided on the lab environment page) then select **Next**.    
    1. Enter the admin password which should be provided on the lab environment page. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.
    

1. On the top left corner of the screen, next to where it says Microsoft Azure, select the Show portal menu icon (the three horizontal lines also referred to as hamburger icon) then select **All Services**.  
1. In the filter services box, enter **Security Center**, then from the results list, select **Security Center**.
1. Notice the information available on the Security center overview page.  

    ![alt text](https://raw.githubusercontent.com/Azure/Azure-Security-Center/main/Labs/Images/asc-dashboard-overview.gif)

1. Information on the top of the page includes the number of Azure subscriptions, the number of Assessed resources, the number of active recommendations, and any security alerts.  On the main body of the page there are cards representing Secure score, Regulatory compliance, Insights, Azure Defender, and more.  
1. From the top of the page, select **Assessed resources**.  This brings you to the inventory page that shows the resources under the subscription. Select **Resource Type - Virtual Machine**

    ![alt text](https://raw.githubusercontent.com/Ritu786/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamentals/stag/Instructions/Images/T1%20S8.png)

1. The Resource health page provides a list of recommendations.  From the available list, select **Management ports of virtual machine should be protected with just-in-time network access control**. 

    ![alt text](https://raw.githubusercontent.com/Ritu786/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamentals/stag/Instructions/Images/T1%20S9.png)

1. Select the drop-down arrow next to Remediation steps. Note how detailed remediation steps are provided along with the option to take action.  

    ![alt text](https://raw.githubusercontent.com/Ritu786/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamentals/stag/Instructions/Images/T1%20S10.png)

1. Select **Security Center** from the top-left corner of the screen to return to the Security Center overview page.
1. From the top of the page, select **Active recommendations**.

    ![alt text](https://raw.githubusercontent.com/Ritu786/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamentals/stag/Instructions/Images/16.png)

1. The recommendations page shows specific actions that can be taken on their potential secure score increase.  Exit the recommendations page by selecting the **X** on top-right corner of the screen.
1. From the main page, select **Regulatory compliance**.
1. The regulatory compliance page provides a list of compliance controls.  Under each control is a set of assessments that are based on the Azure Security Benchmark which provides recommendations on how you can secure your cloud solutions on Azure.

    ![alt text](https://raw.githubusercontent.com/Ritu786/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamentals/stag/Instructions/Images/17.png)

1. Select **IM. Identity Management** then select **IM.4 Use strong authentication controls for all Azure Active Directory based access**.  The list shows customer responsibility actions that can be taken to improve compliance posture.
1. Select the **X** on the top-right corner of the screen to close the page and return to the Security Center Overview page. 
1. Keep the Security center overview page open, you will use in the next task.


#### Task 2: In this task you will navigate to Azure Secure score and explore recommendations that can improve your secure score. 

1. From the Security center overview page, select the **Secure Score** card.

    ![alt text](https://raw.githubusercontent.com/Azure/Azure-Security-Center/main/Labs/Images/asc-overview-secure-score-tile.gif)
    
2. From the recommendations page, select **Manage access and permissions**. Notice that there is one item in that group that is red.
3. Select the item **There should be more than one owner assigned to your subscription**, which shows the resource health status as red. If selecting selecting this item does not work.
    1. From the top-left corner of the page, select **Security Center**, above where it says Recommendations.    
    1. From the left navigation panel, select **Recommendations**.
    1. From the recommendations page, select **Manage access and permissions**. Notice that there is one item in that group that is red.
    1. Select the item **There should be more than one owner assigned to your subscription**, which shows the resource health status as red. 
4. Select the **Azure subscription**.
5. From the top of the Access control (IAM) page, select **+ Add** then from the drop down select **Add role assignment**.
6. In the Role field, enter **Owner**, then select **Owner** from the list below.
7. From the user list, select **Alex Wilber**, then select **Save** on the bottom of the page.
8. It can take up to 24 hours for the status to be updated, after which your secure score will also be updated as all the items in the Manage access and permissions group are satisfied.
9. From the top-left corner of the page, above where is says Azure Pass, select **Security Center** then select **Overview** to return the security center overview page.
10. Keep this page open for the subsequent task.


#### Task 3:  Recall that Security center is offered in two modes: Azure Defender OFF (free) and Azure Defender ON. In this task you discover how to enable and disable Azure Defender.

1.	From the Security center overview page, select the **Enable Azure Defender** from the Azure Defender card.

2.	Select the **Azure Defender on** box.  Notice how all the defender plans change status to On and notice pricing for reach item, then select **Save** from the top-left corner of the page.
3.	Return to the Security center page, by selecting **Security Center** from the top-left corner of the page.   It may take several minutes for the Azure Defender card to reflect the change.  Refresh the page, if necessary.
4.	To disable Azure Defender, select **Pricing & settings** from the left navigation panel of the security center page, select the **Azure Pass – Sponsorship subscription**.
5.	From the Azure Defender plans page, select the **Azure Defender off** box, then select **Save** from the top-left corner of the page.
6.	A pop-up window appears requesting confirmation of the downgrade.  Uncheck the box for Microsoft to contact you and select **Confirm**.
7.	You can now close the browser tab to exit the Azure portal.


#### Review
In this lab, you explored Azure Security Center and learned how Azure Secure Score can be used to improve your organization's security posture.
