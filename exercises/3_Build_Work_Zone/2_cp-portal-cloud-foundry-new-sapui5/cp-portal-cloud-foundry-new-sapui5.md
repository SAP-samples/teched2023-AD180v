# Integrate an SAP Build Apps app to SAP Build Work Zone
<!-- description --> Add an existing SAP Build Apps app to a site in the SAP Build Work Zone, standard edition.

## Prerequisites
 - You've already created the `JobCore` site


## You will learn
  - How to add an existing app to your site

## Intro
In this exercise, you'll use the **Content Manager** to add apps to SAP Build Work Zone.

### Open Content Manager


 Click the Content Manager icon in the side panel to open the **Content Manager**.

> When you open the **Content Manager** you'll see a list of content items that have been added to your subaccount. From here you can manually configure new content items and view any other available content items. You can also access the **Content Explorer** where you can explore exposed content from available channels, select the content, and add it to your own content.

![Open Content Manager](1-open-content-manager.png)


### Create and configure new app


1.  Click **Create** and select **App** from the list.  

  ![Add an app](2-add-app.png)

2. In the header area of the app editor, enter a title `New Orders`.  

  ![Add a title](2a-add-title.png)

3. Under the **Configuration** tab, enter the following values (some will already be there by default):

    * **Open App**: In place

    * **System**: No System

    * **App UI Technology**: URL

    * **URL**: the URL of your app you have created with SAP Build Apps, similar like this one `https://XYZtrial.launchpad.cfapps.us10.hana.ondemand.com/ag30789.ag30789-1.0.0/index.html`

  ![Enter app properties](3-add-app-properties.png)

  

1. Click the **Navigation** tab to specify the intent of your app.

    > The unique combination of a semantic object and an action is called an intent. It is used to define navigation to an application.

2. Enter the following values:

    * **Semantic Object**: `Order`

    * **Action**: `Display`

  ![Add navigation properties](4-navigation-properties.png)

6. Click the **Visualization** tab.

    In this tab, you specify how the app will be displayed in the site.

7. Enter the following values:

      * **Subtitle**: `Create new Sales Orders`

      * **Information**:  `Trigger Approvals`

      * **Icon**: Click the browse icon and select one.

8. On the right, you can see a preview of the tile with all the properties you entered. Click **Save**.

  ![Add visualization properties](5-visualization-properties.png)


### View the app that you created


Go back to the Content Manager by clicking on the breadcrumbs.

![Go back to Content Manager](6-back-to-content-manager.png)

You can see your app in the list of content items:

![View app in content manager list](7-view-app.png)

For end users to access the app in runtime, you must assign the app to a role. 


### Assign the app to the Everyone role


> Content assigned to the `Everyone` role is visible to all users.

1. Click the **Everyone** role.

  ![Select everyone role](8-everyone-role.png)

2. Click **Edit**.

  ![Click Edit](9-edit.png)

3. Under the **Apps** tab, you'll see that your `New Orders` app has an **X** in the **Assignment Status** column. Click the toggle to assign the app to the `Everyone` role.

  ![Assign app to role](10-assign-app-to-role.png)

    
    > If you have many apps, you can type some letters of your app name in the search bar, (for example, `Or`) to search for the app.

4. Click **Save**.


You've successfully created added an app. 

### Next Step

