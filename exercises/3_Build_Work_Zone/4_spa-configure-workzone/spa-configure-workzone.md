
After creating a subscription for SAP Build Work Zone, standard edition in your subaccount, you must now create an SAP BTP service instance for SAP Build Work Zone, standard edition to run in.

1.  Navigate to **SAP BTP Cockpit** subaccount. Select **Services** > **Instances and Subscriptions**. Choose **Create**.

  ![Create instance](014.png)  

2.  For the new instance:
    -  Select **SAP Build Process Automation** as a **Service**.
    -  Select **standard** plan from the **Plan** list.
    -  Select **Cloud Foundry** as **Runtime Environment**.
    -  Select a space from **Space** list.
    -  Set **Instance Name** as **SPA-instance**.
    -  Choose **Create**. 

  ![Instance](015.png)

3. The instance was added.

  ![Instance](016b.png)

### Create a Service Key for the SAP Build Process Automation Instance

You can use service keys to generate credentials to communicate directly with a service instance. Once you configure them for your service, local clients, apps in other spaces, or entities outside your deployment can access your service with these keys.

> **CAUTION**: If you are using a Free Tier account, please skip this step. The service Key is automatically created.
  
<!-- border -->![Service key](085.png) 

1. In your SAP BTP subaccount, under **Services**> **Instances and Subscriptions**, select the instance that you created above.

  ![Select instance](016c.png)

2. On the details screen that opens, choose **Service Keys**> **Create**.

  ![Create service key](016d.png)

3. On the creation screen, enter any name for your service key.

4. Optional. Upload a JSON file.

5. Choose **Create**.

  ![Create service key](016e.png)

    The service key is created and you can view the credentials. 

  ![View credentials](016f.png)

6. Once you open it, download the json file.

    > You will need these credentials to configure destinations.

  ![View credentials](01.png)

### Configure SAP Build Process Automation Destination


Before developing with SAP Build Process Automation or for configuring SAP Build Work, standard edition for use with SAP Build Process Automation, you must create an SAP BTP destination for your subaccount.

> You have created a service instance and service key for SAP Build Process Automation and noted down the service key credentials for configuring this destination.

1. Choose **Connectivity**> **Destinations**> **New Destination**.

  ![New destination](01a.png)

2. Choose **Blank Template**, and enter the following details from the downloaded json file:

    > CAUTION: When copying the values for URL, Client ID, Client Secret and Token Service URL, please select the values without the quotes and paste them in the destination template. 

    |  **Field**    | **Value**
    |  :------------- | :-------------
    | Name      |  `sap_process_automation_service`
    | Type       | HTTP
    | Proxy Type       | Internet
    | Authentication      | `OAuth2ClientCredentials`
    | URL      |    `<"endpoints"."api">`
    | Client ID       | `<"uaa"."clientid">`
    | Client Secret | `<"uaa"."clientsecret">`
    | Token Service URL | `<"uaa"."url">` add /`oauth`/token
    
    For your values, please refer to screenshot below:

  ![New destination](01b.png)


3. Add additional properties copied from the service key:

    > CAUTION: When copying the values for`saasregistryenabled`, `sap.cloud.service` and `sap.cloud.service.alias`, please select the values without the quotes.

    |  **Field**    | **Value**
    |  :------------- | :-------------
    |  `endpoints`        | `endpoints` copy the whole JSON structure including `{` and `}`
    |  `html5-apps-repo`       | `html5-apps-repo` copy the whole JSON structure including `{` and `}`
    |  `saasregistryenabled`        | `saasregistryenabled`
    |  `sap.cloud.service`        | `sap.cloud.service`
    |  `sap.cloud.service.alias`        | `sap.cloud.service.alias`

    For your values, please refer to the screenshot below:

  ![New destination](01c.png)

4. **Save** your changes.

  ![New destination](01d.png)

5. Test the destination by selecting **Check Connection**.

  ![New destination](01e.png)



### Assign roles for SAP Build Work Zone, standard edition

Once you have created a destination, you must now assign roles to any users who need access to that destination (including your own user account).

1. Navigate to **SAP BTP Cockpit** subaccount > **Security** > **Users**.

  ![navigate to Users](Step3-1.png)

2.  Select the user to whom you will give the roles then on **Enter Full-Screen Mode** .

  ![Select user](Step3-2.png)

3.  Choose **Assign Role Collection**.

  ![Assign Role Collection button](Step3-3.png)

4.  Select **Launchpad Admin** and **Launchpad External User** then choose **Assign Role Collection**. 

    > **Launchpad Admin** is the role for whom is going to design the Business Site in the Business Site editor. Launchpad Admin should not be given to all users for security purposes.
    
    > **Launchpad external user** is the role for whom accesses the final Business Site. 

  ![Select Roles](Step3-4.png)

    The roles are assigned. 

  ![Result assignation](Step3-5.png)


### Open and manage SAP Build Work Zone Application

1.  Navigate back to **SAP BTP Cockpit** subaccount. Choose **Services** then **Instances and Subscriptions**. Choose **Go to Application** next to **SAP Build Work Zone, standard edition**.

  ![SBWSE](018.png) 

2. The Site Manager is now ready to use. Select **Channel Manager**.

  ![SBWSE](031.png)

3.  Choose **Update Content**.

  ![SBWSE](032.png)
    
    > The content updates and the status changes to Updated.

4.  Select **Content Manager**. On the top tabs select **Content Explorer** and then select **HTML5 Apps**.

  ![SBWSE](033.png)
    
  ![SBWSE](033b.png)

5.  Select all items and click **Add**.

  ![SBWSE](034.png)

6.  Navigate to **Content Manager**. Choose **Create** and select **Group**.

  ![SBWSE](040.png)
    
  ![SBWSE](040a.png)

7.  Manage the Group:
    - Set **Title** to **SAP Build Process Automation**.
    - Click on the search field to display item results.
    - Assign **My Inbox** and **Process Workspace** to the group.
    - Choose **Save**.
    - Go back to **Content Manager**. 

  ![SBWSE](041.png)

8.  Select **Everyone** item to edit it. Select **Edit** to edit role.

  ![SBWSE](042.png)

  ![SBWSE](043.png)

9.  Manage changes:

    - Assign **My Inbox**, **Process Workspace**, **Visibility Scenario Dashboard** and **Visibility Scenario Instances** to **Everyone** role.
    - Choose **Save**.

  ![SBWSE](044a.png)


---
