# Building Resources using the Azure Resource Manager

### Exercise 1: Signing in to the Azure Portal

1. Log into the **Azure Portal**.

    >Note: The lab platform will give you a username and password that you can use to sign-in to the Azure Portal. Please use this username and password for the labs instead of your own company-supplied username and password.

1. In the top center of the **Home** view, select **Dashboard** as your default view and click **Save**.

1. In the navigation pane on the left side, click **Dashboard**.

### Exercise 2: View Resource Groups

#### Task 2: View a Resource Group using the Cloud Shell and Azure CLI

1.  At the top of the portal, click the **Cloud Shell** icon to open a new shell instance.

    > **Note**: The **Cloud Shell** icon is a symbol that is constructed of the combination of the *greater than* and *underscore* characters.

1.  Because this is your first time opening the **Cloud Shell** using your *Azure Pass* subscription, you will see a wizard to configure **Cloud Shell** for first-time usage. Perform the following actions:

    a.  When offered a choice between **Bash** or **PowerShell**, select the **Bash** option.

    b.  You will then see a dialog prompting you to create a new **Storage Account** to begin using the shell. You can safely accept the default settings and click the **Create storage** button.

    c.  Wait for the **Cloud Shell** to finish its first-time setup procedures before moving on with the lab.

    > If you do not see the configuration options for **Cloud Shell**, this is most likely because you are using an existing subscription with this course's labs. The labs are written from the perspective that you are using a new Azure Pass subscription. You may see some small discrepancies in future lab instructions.

1.  In the **Cloud Shell** command prompt at the bottom of the portal, type in the following command and press **Enter** to view a list of possible CLI commands:

    ```azurecli-interactive
        az --help
    ```

1.  Type in the following command and press **Enter** to view a list of possible CLI commands for *Resource Groups*:

    ```azurecli-interactive
        az group --help
    ```

1.  Type in the following command and press **Enter** to view a list of possible CLI commands to *list Resource Groups*:

    ```azurecli-interactive
        az group list --help
    ```

1.  Type in the following command and press **Enter** to list all resource groups in the subscription:

    ```azurecli-interactive
        az group list
    ```

1. Close the **Cloud Shell** prompt at the bottom of the portal.

### Exercise 3: Deploy a Minimal Template

#### Task 1: Deploy Storage Account ARM Template

1.  On the left side of the portal, click the **Create a resource** link.

1.  At the top of the **New** blade, locate the **Search the Marketplace** field.

1.  Enter the text **Template Deployment** into the search field and press **Enter**.

1.  In the **Everything** search results blade, select the **Template deployment** result.

1.  In the **Template deployment** blade, click the **Create** button.

1.  In the **Custom deployment** blade, click the *Build your own template in the editor* link.

1.  In the **Edit template** blade, locate the text editor and delete the existing template content.

1.  Copy and paste the following ARM template into the template editor:

    ```json
        {
            "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentTemplate.json#",
            "contentVersion": "1.0.0.0",
            "resources": [
                {
                    "apiVersion": "2015-06-15",
                    "name": "[concat('stor', uniqueString(resourceGroup().id))]",
                    "type": "Microsoft.Storage/storageAccounts",
                    "location": "[resourceGroup().location]",
                    "properties": {
                        "accountType": "Standard_LRS"
                    }
                }
            ]
        }
    ```

1.  Click the **Save** button to persist the template.

1. Back in the **Custom deployment** blade, perform the following actions:

    a.  Leave the **Subscription** field set to its default value.

    b.  In the **Resource group** section, locate the list and select the **Azurelod8028054** option.

    c.  In the **Terms and Conditions** section, select the *I agree to the terms and conditions stated above* checkbox.

    d.  Click the **Purchase** button.

1. Wait for the creation task to complete before moving on with this lab.

#### Task 2: View Deployment Metadata

1.  On the left side of the portal, click the **Resource groups** link.

1.  In the **Resource groups** blade, locate and select the **Azurelod8028054** *Resource Group* link.

1.  In the **Azurelod8028054** blade, locate the **Settings** section on the left side of the blade and click the **Deployments** link.

1.  In the **Deployments** pane, select the latest deployment to view its metadata in a new blade.

1.  Within the deployment blade, observe the information displayed in the **Operation details** section.

> **Review**: In this exercise, you deployed a minimal ARM template that created a deployment using a simple ARM template that deployed a single resource without any input or output values.

### Exercise 4: Deploy a Simple Template

#### Task 1: View ARM Template

1.  Right click the link [here](files/deploy.json) and select **Save As** to download the needed **deploy.json** file.

1.  Right-click the **deploy.json** file you just downloaded and select the **Open with Code** option to start the **Visual Studio Code** application.

1.  In the **Visual Studio Code** window that appears, observe the content of the JSON file.

1.  At the top of the **Visual Studio Code** window, click the **File** menu and select the **Close Folder** option.

1.  Close the **File Explorer** window.

7.  Return to the **Microsoft Edge** window with the **Azure Portal** open.

#### Task 2: Deploy App Service ARM Template

1.  On the left side of the portal, click the **New** link.

2.  At the top of the **New** blade, locate the **Search the Marketplace** field.

3.  Enter the text **Template Deployment** into the search field and press **Enter**.

4.  In the **Everything** search results blade, select the **Template deployment** result.

5.  In the **Template deployment** blade, click the **Create** button.

6.  In the **Custom deployment** blade, click the *Build your own template in the editor* link.

7.  In the **Edit template** blade, click the **Load file** link.

8.  In the **Open** file dialog that appears, navigate to the **Allfiles (F):\\Mod02\\Labfiles\\Starter** folder.

9.  Select the **deploy.json** file.

10. Click the **Open** button.

11. Back in the **Edit template** blade, click the **Save** button to persist the template.

12. Back in the **Custom deployment** blade, perform the following actions:

    a.  Leave the **Subscription** field set to its default value.

    b.  In the **Resource group** section, locate the list and select the **APPSGROUP** option.

    c.  In the **Function App Name** field, enter a globally unique value. This will be used to create the unique URL for this *Function App*.

    d.  In the **Terms and Conditions** section, select the *I agree to the terms and conditions stated above* checkbox.

    e.  Click the **Purchase** button.

13. Wait for the creation task to complete before moving on with this lab.

#### Task 3: View Deployment Metadata

1.  On the left side of the portal, click the **Resource groups** link.

2.  In the **Resource groups** blade, locate and select the **APPSGROUP** *Resource Group* link.

3.  In the **APPSGROUP** blade, locate the **Settings** section on the left side of the blade and click the **Deployments** link.

4.  In the **Deployments** pane, select the latest deployment to view its metadata in a new blade.

5.  Within the deployment blade, observe the information displayed in the **Inputs** and **Outputs** sections.

> **Review**: In this exercise, you deployed a more sophisticated template that created multiple resources using a combination of parameters, variables and output values.
