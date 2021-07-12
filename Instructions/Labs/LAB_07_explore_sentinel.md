---
lab:
    title: 'Explore Azure Sentinel'
    module: 'Module 3 Lesson 3: Describe the capabilities of Microsoft security solutions: Describe security capabilities of Azure Sentinel'
---


# Lab: Explore Azure Sentinel 

## Lab scenario
In this lab you will walk through the process of creating an Azure Sentinel instance.  You will also set up the permissions to ensure access to the resources that will get deployed to support Azure Sentinel.  Once this basic setup is done you will walk through the steps for connecting Sentinel to your data sources, use built-in analytics to get notified of anything suspicious, and lastly you will explore the automation capability.  

  

**Estimated Time**: 30-45 minutes

#### Task 1:  Create an Azure Sentinel instance.

1. Open Microsoft Edge. In the address bar enter **portal.azure.com**.

2. Sign in with your admin credentials.
    
    1. In the Sign in window enter **odl_user_XXXXXX@cloudlabsai.com** (where XXXXXX is your unique ID provided on the lab environment page) then select **Next**.    
    1. Enter the admin password which should be provided on the lab environment page. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.
    

3. On the top left corner of the screen, next to where it says Microsoft Azure, select the Show portal menu icon (the three horizontal lines also referred to as hamburger icon) then select **All Services**.  

4. In the filter services box, enter **Sentinel**, then select **Azure Sentinel** from the list.

5. From the Azure Sentinel page, select **Create Azure Sentinel**.

6. From the Add Azure Sentinel to a workspace page, select **Create a new workspace**.

7. From the basics tab of the Create Log Analytics workspace, enter the following:
    1. Subscription:  **Select the given subscription**   
    1. Resource group: select **Create New**, then enter the name **SC900-ResourceGroup** then select **OK**.
    1. Name: **SC900-LogAnalytics-workspace**.
    1. Region: **East US** (leave this default)
    1. Select **Next: Pricing tier >**

    ![alt text](https://raw.githubusercontent.com/CloudLabs-MOC/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamentals/prod/Instructions/Images/15.png)

8. For the Pricing Tier, leave the default settings: **Pay-as-you-go (per GB 2018)**, then select **Next: Tags >**.

9. For the Tags, you can leave this blank, then select **Review + Create**.

10. Verify the information you entered then select **Create**.

11. If you don’t see the new workspace listed, select **Refresh**, then select **Add**.

    ![alt text](https://raw.githubusercontent.com/Ritu786/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamentals/stag/Instructions/Images/19.png)

12. Once the new workspace is added, the Azure Sentinel | News & guides page will display.  Note the three steps listed on the Get started page.

    ![alt text](https://raw.githubusercontent.com/Ritu786/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamentals/stag/Instructions/Images/20.png)

13. Keep this page open, as you will use it in the next task.

#### Task 2:  With the Azure Sentinel instance created, you will want to make sure that you have the necessary access to the resources that get deployed to support Azure Sentinel.  In this task you will go to the access control (IAM) page for the resource group that you created with the instance of Azure Sentinel, view the available roles, and assign yourself (MOD administrator) the required role. Assigning the role at the resource group level will ensure the role will apply to all the resources that are deployed to support Azure Sentinel.

1. From the Azure Sentinel page, on the top-left corner of the page, above where is says Azure Sentinel, select **All Services**.

2. In the filter services box, enter resource groups, then from the list provided select **Resource groups**.

3. From the Resource groups page, select the resource group that you created with Azure Sentinel, **SC900-ResourceGroup**.

4. From the SC900-ResourceGroup page, select **Access control (IAM)** from the left navigation panel.

5. From the Access control page, select **View my access**.  Note the current role is Owner.  Close the assignments window by selecting the **X** on the top-right corner of the window.

    ![alt text](https://raw.githubusercontent.com/CloudLabs-MOC/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamentals/prod/Instructions/Images/7-1.png)

6. If the the role is not owner then follow the below steps:

    1. From the Access control page, select **+Add**, then select **Add role assignment**.

    1. The Add role assignment window opens.  Select the drop-down arrow in the Select a role field to display the available roles.  For this lab, select **Owner**.  NOTE:  As a best practice you should assign the least privilege required for the role.  As a reference, review permissions in Azure Sentinel:  https://docs.microsoft.com/en-us/azure/sentinel/roles

    1. From the list of users displayed, select **UserName** given on the lab environment page.

    1. Select **Save** at the bottom of the page.

    1. From the access control page, select **View my access** to confirm the owner role has been added, then close the window by select the **X** on the top-right corner of the window.

8. Return to the All services page of Azure, by selecting **All Services** from the top-left corner of the page, above where it says Resource groups.

#### Task 3:  In this task you will walk through the process of connecting Azure Sentinel to your data source to begin to collect data. Note: it can take a bit time to show the connected status of a connector (~30 minutes, depending on the tenant).

1. In the Filter services box of the All services page, enter **Log Analytics Workspace**, then select **Azure Sentinel** from the results list. 

2. From the Azure Sentinel page, select the workspace you created with the instance of Azure Sentinel, **SC900-LogAnalytics-workspace**.

3. The first step with Azure Sentinel is to be able to collect data. From the left navigation panel select **Data connectors**, listed under configuration.

    ![alt text](https://raw.githubusercontent.com/Ritu786/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamentals/stag/Instructions/Images/23.png)

4. From the Data connectors page, scroll down on the main window to view the extensive list of available connectors. In the Search box of the data connectors page, enter **Azure** then from the list select **Azure Active Directory**.

    ![alt text](https://raw.githubusercontent.com/Ritu786/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamentals/stag/Instructions/Images/24.png)

5. The Azure Active Directory connector window opens.  Select **Open connector page**.

6. From the Azure Active Directory connector page, review the description and note the related content which includes workbooks, queries, and Analytic rules templates.  

7. The instructions tab in the main window, provides the perquisites for Azure Sentinel to integrate with Azure Active Directory.   Under configuration, select **Sign-in logs** then select Apply Changes (multiple connectors can be chosen).

    ![alt text](https://raw.githubusercontent.com/CloudLabs-MOC/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamentals/prod/Instructions/Images/7-2.png)

8. From the Next steps tab, note the list of recommended workbooks.   Under recommended workbooks, select **Azure Sign-in logs** (additional workbooks can be chosen).

    ![alt text](https://raw.githubusercontent.com/CloudLabs-MOC/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamentals/prod/Instructions/Images/7-3.png)

9. From the workbooks page and with the templates tab selected (underlined), select **Azure Sign-in logs**. 

10. From the Azure AD Sign-in logs window that opens, review the description, and select **View template**.  Exit out of the template, by selecting the **X** on the top-right corner of the screen.  Select **Save** from the bottom of the page, then select **OK** to save the workbook to the default location.

    ![alt text](https://raw.githubusercontent.com/CloudLabs-MOC/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamentals/prod/Instructions/Images/7-4.png)

11. From the top-left corner of the Workbooks page, above where it says Workbooks, select **Azure Sentinel**. This returns you to the Azure Sentinel Data Connectors page.

12. The top of the Data connectors page should display 1 connected, to reflect that you are now connected to Azure Active Directory.

13. From the left navigation panel, select **Workbooks**.

14. From the Workbooks page, select the **My workbooks** tab, which is above the search box.  The workbook you just saved is listed and available for you to view and monitor your data.

    ![alt text](https://raw.githubusercontent.com/CloudLabs-MOC/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamentals/prod/Instructions/Images/7-5.png)

15. Keep this page open, as you will use it in the next task.

#### Task 4:  In this task you will walk through the process of using a built-in analytics rule template to create a rule to get notified when something suspicious occurs.

1. From the left navigation panel, select **Analytics**.

2. The Analytics page will show active rules (Advanced multistage attack detection is enabled by default) and will also provide access to Rule templates.  Select the **Rule templates** tab.  Notice the list of available templates and the different ways to filter the list.  Using built-in analytics alerts within the Azure Sentinel workspace, you’ll get notified when anything suspicious occurs.

3. In the Search bar, enter **Azure Portal**.  Select **Failed login attempts to Azure Portal**.  

4. From the window that opens, read the description and review the information associated with the template.  Select **Create rule** on the bottom of the page.

    ![alt text](https://raw.githubusercontent.com/Ritu786/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamentals/stag/Instructions/Images/25.png)

5. From the Analytics rule wizard, review the information, then select **Next: Set rule logic >**.

6. The Set rule logic page, is where you define the logic for your new analytics rule. The template already provides some logic and predefined settings.  Scroll through the page to see the available settings.  Leave the defaults. Select **Next: Incident settings (preview)>**.

7. With Incident settings, Azure Sentinel alerts can be grouped together into an Incident that should be looked into. You can set whether the alerts that are triggered by this analytics rule should generate incidents.  Leave the default settings and select **Next: Automated response >**.

8. In the Automated response tab, note how you can add a playbook to automate the response.  Similarly, you can create an incident automation rule.  Select **+ Add** new under incident automation.  A window to create a new automation rule opens.  Any automation rule you create on this page is triggered by the analytics rule you are c   Note that you can add conditions and set actions for the rule.   Select **Cancel** to exit out of the window.

    ![al text](https://raw.githubusercontent.com/Ritu786/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamentals/stag/Instructions/Images/26.png)

9. Select **Next: Review>** to review all the details associated with the rule and based on the chosen template. At this point, you can choose to create the rule, by selecting **Create** or exit without creating the rule by selecting **X** on the top-right corner of the page.

10. Keep this page open, as you will use it in the next task.

#### Task 5:  In the previous task you created an analytics rule to be alerted of suspicious activities.  Embedded in that wizard is the option to automate the response to an incident based on the specific rule.  But you can also create automation rules by going directly to the automation configuration option.

1. From the left navigation panel, select **Automation**.  

2. Select **+ Create**. From the drop-down note how you can select either to add a new playbook or add a new rule.  Select **Add new rule**.  

    ![alt text](https://raw.githubusercontent.com/Ritu786/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamentals/stag/Instructions/Images/27.png)

3. A window to create a new automation rule opens.  Note that you can add conditions and set actions for the rule.  The only distinction is that the first condition is to associate the analytics rule(s) to which you want to apply this automation rule.  This is was greyed out in the previous task because the automation was being configured for the specific rule.  Select **Cancel** to exit out the Create new automation rule window.

4. Keep this page open, as you will use it in the next task.


#### Task 6:  Delete Azure Sentinel Resource group.  Azure Sentinel is billed based on the volume of data ingested for analysis in Azure Sentinel. Although the amount of data ingested as a result of this lab is minimal, it is recommended that you delete the Azure Sentinel resource group when you are done exploring the features of capabilities of Azure Sentinel.

1. From the Azure Sentinel page, on the top-left corner of the page, above where is says Azure Sentinel, select **All Services**.

2. In the filter services box, enter resource groups, then from the list provided select **Resource groups**.

3. From the Resource groups page, select the resource group that you created with Azure Sentinel, **SC900-ResourceGroup**.

4. From the top center of the page, select **Delete resource group**.  Review the warning.  Enter the resource group name, **SC900-ResourceGroup**, then select **Delete** from teh bottom of the page.  It will take several minutes to delete the resource group.

5. Once you have verified the resource group was deleted, close the browser page. 


#### Review

In this lab you walked through the process of creating an Azure Sentinel instance.  You also set up the permissions to ensure access to the resources associated with your instance of Azure Sentinel.  With your Azure Sentinel instance created, you walked through the steps for connecting Sentinel to your data sources, using built-in analytics rules to get notified of anything suspicious, and lastly you explored the automation capability. You concluded the lab by deleting the resource group associated with the instance of Azure Sentinel that you created.
