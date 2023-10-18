# Deploy app from SAP Build App to SAP BTP
<!-- description --> Deploy an app created with SAP Build Apps to HTML5 applications on SAP BTP.

 
## Prerequisites
- To deploy, you need to be a member of the Cloud Foundry org and space to which you will be deploying to.


## You will learn
- How to deploy an app created with SAP Build Apps to SAP BTP



## Intro
After creating an app in SAP Build Apps, and after viewing the preview on the web, you can deploy it directly to SAP BTP, like any other HTML5 application.

As of the writing of this exercise, you could only deploy to an Cloud Foundry org's default space.

>**IMPORTANT:** You need to be a member of the Cloud Foundry org and space to which you will be deploying to. Which you normally are.

>As you are an admin of the SAP BTP trial subaccount, you can see who is an org member by going to the cockpit and navigating to **Cloud Foundry > Org Members**.

>![Org members](CFForgmember.png)


---


### Build the app
1. Open the **Launch** tab.
   
2. Select **Open Build Service**.
   
    ![Build service](build1.png)


3. Underneath Web App click **Build**.

    ![Click Build](build1a.png)

4. Select **MTAR**.
   
    Select the most current runtime version.

    Enter a version for your app, for example `1.0.0`.

    ![Settings](build2.png)

5. Click **Build**.

The build may take a a little while (20 minutes or so). Take a breath and have a break.
If you refresh the page, the status will change from `created` to `queued` to finally `delivered`.

![Build status](build3.png)

### Deploy app
Before deploying, you must have a build showing as `delivered`.

![Delivered status](deploy1.png)

1. Click **Deploy MTA**.

    The first you deploy, you will get the following to sign in to Cloud Foundry so you can deploy the app.

    ![Authorize](deploy2.png)

    >If you have rights to Cloud Foundry on more than 1 BTP tenant, you will need to choose the environment. Otherwise, the environment will automatically be chosen. 

2. Click **Authorize BTP Deployments**.

    You will get a dialog for signing in to the deployment environment (Cloud Foundry).
    
    ![Origin key](originkey.png)


**!!!!to be changed!!!!**


    >Since SAP Build Apps requires a custom identity provider (or, IDP, the service that lets you sign into to BTP), you will sign in with the custom identity provider. To do this, you must provide the code for the specific provider.

3. Enter your custom IDP origin key in the input box – which for many workshops, will be `am86fwfbe-platform` or `sap.custom` – and then click **Sign in with alternative identity provider**.
    
3. Once signed in, select the Cloud Foundry organization to deploy the app to.

    >**For SAP Build workshops**, this will `Work Zone Training _training-emea-z3ktmhk1`.

    ![Select org](deploy4.png)

    >The deployment is always to the default space of the organization.

4. Click **Deploy MTA**.

    ![Deploy MTA](deploy5.png)

    The screen will show a running list of log messages ... this could take about 2 minutes.

    ![Log messages](deploy6.png)

    Once it is done, you will get a screen like this:

    ![Alt text](deploy7.png)

    The name of the app is at the end of the URL, for example, above in the picture, `ag3278`.

    >**IMPORTANT:** As of the writing of this tutorial, the link in this screen did not work.
    >
    >Generally the link will be in this format:
    >
    >`https://<tenant subdomain>.launchpad.cfapps.eu10.hana.ondemand.com/<app name>.<app name>-<version>/page.Page1.html`
    >
    >The app name is generally in the format `ag1234`. So an example URL is:
    >
    >`https://mysubaccount-f5ytahk1.launchpad.cfapps.eu10.hana.ondemand.com/ag5633.ag5633-1.0.0/page.Page1.html`
    >
    >In any event, you can get the correct link in the BTP cockpit, as long as you have the app name in the link, such as above `ag5633`.

### Run app
1. Open your subaccount's cockpit.

2. Go to **HTML5 Applications**, and find your app.

    ![HTML5 Applications](run1.png)

    Click the application link (save this link if you later want to embed the app in SAP Build Work Zone).

    You should now see your application.
