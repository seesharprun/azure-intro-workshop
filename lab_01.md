# Navigating the Azure Portal

### Exercise 1: Signing in to the Azure Portal

The lab platform will give you a username and password that you can use to sign-in to the Azure Portal. Please use this username and password for the labs instead of your own company-supplied username and password.

### Exercise 2: Customizing the Azure Portal

#### Task 1: Customize the Dashboard

1. After the dashboard is fully loaded, right-click the **Dashboard** (home screen), and then click **Edit**.

1. In the **Tile Gallery**, drag the *Service Health* tile onto your dashboard.

1. At the top of the tile, click the button with three ellipses *“…”*.

1. Select the **2x4** size option.

1. In the **Tile Gallery**, drag the *Markdown* tile onto your dashboard.

1. In the **Content** section of the **Edit Markdown** dialog that appears, update the content with the following markup:

	```
	# Account Details:
	## Corporate Account
	Account **&#35;&#52;&#55;&#57;** is managed by the ``IT department``.
	> &copy;2016
	```

1. Click the **Done** button.

1. Right-click the **Dashboard** (home screen), and then click **Done customizing**.

#### Task 2: View a blade

1. In the navigation pane on the left side, click **All services**.

1. Within the list located in the panel that displays, click **Subscriptions**.

1. Observe the **Subscriptions** blade that displays.

1. In the top menu bar, click the gear icon.

1. Observe the **Portal Settings** blade that displays.

#### Task 3: Begin a journey

1. At the top-left corner of the screen, click **Create a resource**.

1. In the **New** panel that displays, click the **See all** link next to the **Azure Marketplace** header.

1. In the **Marketplace** blade that displays, click **Web**.

1. In the **Web** blade that displays, locate the search box at the top of the blade, type in the text **starter** and then press *Enter*.

1. In the search **results**, locate and select the **ASP.NET Starter Web App** option.

1. In the **ASP.NET Starter Web App** blade that displays, click **Create**.

1. In the next **ASP.NET Starter Web App** blade that displays, click the **App Service plan/Location** option.

1. In the App Service Plan blade, click the **Create New** button.

1. Provide a name for your new **App Service Plan**.

1. Scroll to the left, and click the close (**X**) button on the first **ASP.NET Starter Web App** blade to close the journey.

1. In the **Message from webpage** Internet Explorer dialog box, click **OK**.

#### Task 4: Reviewing Tiles

1. Click **Microsoft Azure** in the upper-left corner to return to the dashboard.

1. Click the **Service Health** tile, and then, in the resulting blade, note the **Service Health - Service Issues** view. Click **Planned maintenance**, **Health advisories**, and **Resource health**. Note that you can customize each view by filtering categories of items that you are interested in, such as region, service type, or resource type.  

1. Click **Microsoft Azure** in the upper-left corner to return to the dashboard.

1. If needed, to expand the hub menu, click the double caret icon directly underneath the **Microsoft Azure** label.

1. In the hub menu, click **+ Create a resource**.

1. On the **New** blade, review the list of available options, but do not select any.

1. In the hub menu, click **All services**, in the **All services** text box, type **Subscriptions**, and press **Enter**.

1. In the list of results, click **Subscriptions**.

1. On the **Subscriptions** blade, right-click the entry that represents your subscription, and then click **Pin to dashboard** in the context menu.

1. Click the **Notification** icon (bell) in the horizontal bar in the upper-right part of the portal page, and then verify that the subscription tile was pinned to dashboard successfully.

1. Close the **Notifications** pane.

1. Click **Microsoft Azure** in the upper-left corner to return to the dashboard.

1. Verify that a new tile that represents your subscription appears on the dashboard.

> **Results**: After completing this exercise, you will have viewed blades, journeys, and journey parts.

### Exercise 3: Create a Marketplace Virtual Machine

#### Task 1: Create a VM
  
1. In the hub menu on the left side of the portal page, click **+ Create a resource**.

1. On the **New** blade, click **Compute** and then click **Windows Server 2016 Datacenter**.

1. On the **Basics** tab of the **Create a virtual machine** blade, specify the following settings, and then click **Next: Disks**:

    - Subscription: ensure that the name of the target Azure subscription appears in the drop-down list

    - Resource group: click **Create new**, in the **Name** text box, type **VIRTUALMACHINEGROUP**, and click **OK**.

    - Virtual machine name: **demo-vm**
  
    - Region: select the name of the Azure region that is available in your subscription and which is closest to the lab location

    - Availability options: **No infrastructure redundancy required**

    - Image: **Windows Server 2016 Datacenter**

    - Size: accept the default size

    - Username: **Student**

    - Password: **Pa55w.rd1234**

    - Confirm password: **Pa55w.rd1234**

    - Public inbound ports: click **Allow selected ports**

    - Select inbound ports: **RDP**
  
    - Already have a Windows license: **No**

1. On the **Disks** tab of the **Create a virtual machine** blade, specify the following settings, and then click **Next: Networking**:

    - OS disk type: **Standard HDD** 

    - Use managed disks: **Yes**

1. On the **Networking** tab of the **Create a virtual machine** blade, specify the following settings, and then click **Next: Management**:

    - Virtual network: accept the default value (this will create a new virtual network)

    - Subnet: accept the default value (this will create a /24 subnet named **default** within the IP address space of the virtual network)

    - Public IP address: **(new) demo-vm-ip**

    - Network security group: **Basic**

    - Public inbound ports: **Allow selected ports**

    - Select inbound ports: **RDP**

    - Accelerated networking: **Off**

1. On the **Management** tab of the **Create a virtual machine** blade, specify the following settings, and then click **Next: Guest config**:

    - Boot diagnostics: **On**
  
    - OS guest diagnostics: **Off**
  
    - Diagnostics storage account: accept the default value (this will create a new storage account)

    - Managed service identity: **Off**

    - Extensions: **No extensions**
  
    - Enable auto-shutdown: **Off**

    - Enable backup: **Off**

1. On the **Guest config** tab of the **Create a virtual machine** blade, accept the default settings, and then click **Next: Tags**.

1. On the **Tags** tab of the **Create a virtual machine** blade, accept the default settings, and then click **Next: Review + create**.

1. On the **Review + create** tab of the **Create a virtual machine** blade, review the list of settings and click **Create**.

1. Review the **Your deployment is underway** blade. 

1. Wait for the deployment to complete. 

    > **Note**: The deployment may take approximately 5 minutes. 

#### Task 2: Verify VM creation
  
1. In the Azure Portal, on the **Your deployment is complete** blade, click **Go to resource**.

1. On the **demo-vm** blade, click **Activity log**. This will display the blade allowing you to search for activities affecting the VM that you or other admins carried out.

    > **Note**: The list of events should include a single entry corresponding to the creation of the virtual machine. Activities represent changes to the state of the VM that you or other admins carried out, such as restarting it. 

1. At the top of the menu options for the Azure VM, click **Overview**.

1. In the list of menu options, scroll down to the **Support + troubleshooting** section and click **Resource health**.

1. Verify that there are no known Azure platform problems affecting this VM. Click **Refresh** if you receive a message stating **Resource health unknown**.

> **Result**: Once you completed this exercise, you have deployed a Microsoft Azure VM from the Azure Portal by using a Windows Server 2016 Datacenter Azure Marketplace image, as well as reviewed activity logs and resource health of the VM.

### Exercise 4: Exploring the Azure Cloud Shell

#### Task 1: Open the Cloud Shell

1. At the top of the portal, click the **Cloud Shell** icon to open a new shell instance.

    > **Note**: The **Cloud Shell** icon is a symbol that is constructed of the combination of the *greater than* and *underscore* characters.

1. Because this is your first time opening the **Cloud Shell** using your *Azure Pass* subscription, you will see a wizard to configure **Cloud Shell** for first-time usage. Perform the following actions:

    a. When offered a choice between **Bash** or **PowerShell**, select the **Bash** option.

    a. You will then see a dialog prompting you to create a new **Storage Account** to begin using the shell. You can safely accept the default settings and click the **Create storage** button.

    a. Wait for the **Cloud Shell** to finish its first-time setup procedures before moving on with the lab.

    > If you do not see the configuration options for **Cloud Shell**, this is most likely because you are using an existing subscription with this course's labs. The labs are written from the perspective that you are using a new Azure Pass subscription. You may see some small discrepancies in future lab instructions.

#### Task 2: Test Cloud Shell

1. In the **Cloud Shell** command prompt at the bottom of the portal, type in the following command and press **Enter** to view a list of possible CLI commands:

    ```
    az --help
    ```

1. Type in the following command and press **Enter** to view a list of possible CLI commands for *Resource Groups*:

    ```
    az group --help
    ```

1. Type in the following command and press **Enter** to view a list of possible CLI commands to *create a Resource Group*:

    ```
    az group create --help
    ```

1. Type in the following command and press **Enter** to view a list of possible CLI commands to *list Resource Groups*:

    ```
    az group list --help
    ```

#### Task 3: Create App Service Plan

2.  In the **Cloud Shell** command prompt at the bottom of the portal, type in the following command and press **Enter** to create a new **Resource Group**:

    ```azurecli-interactive
    az group create --name APPSERVICEGROUP --location eastus
    ```

4.  Type in the following command and press **Enter** to view a list of possible CLI commands for *App Service*:

    ```azurecli-interactive
    az appservice --help
    ```

5.  Type in the following command and press **Enter** to view a list of possible CLI commands for *App Service Plans*:

    ```azurecli-interactive
    az appservice plan --help
    ```

6.  Type in the following command and press **Enter** to view a list of possible CLI commands to *create App Service Plans*:

    ```azurecli-interactive
    az appservice plan create --help
    ```

7.  Type in the following command and press **Enter** to create a new **App Service Plan**:

    ```azurecli-interactive
    az appservice plan create --is-linux --name HostedServicePlan --resource-group APPSERVICEGROUP --location eastus --sku B2

#### Task 4: Create a Web App Instance

1.  Type in the following command and press **Enter** to view a list of possible CLI commands for *Web Apps*:

    ```azurecli-interactive
    az webapp --help
    ```

2.  Type in the following command and press **Enter** to view a list of possible CLI commands to *create Web Apps*:

    ```azurecli-interactive
    az webapp create --help
    ```

3.  Type in the following command and press **Enter** to view a list of possible *runtimes* for a *linux-based az webApp Service* instance:

    ```azurecli-interactive
    az webapp list-runtimes --linux
    ```

4.  Type in the following command and press **Enter** to create a new blank **Web App** using a unique name:

    ```azurecli-interactive
    az webapp create --name [Unique Name Here] --plan HostedServicePlan --resource-group APPSERVICEGROUP --runtime "DOTNETCORE|2.0"
    ```

    Make sure you replace the **\[Unique Name Here\]** placeholder with a globally unique name. For example, if your unique name is **blankinterestingapp**, your command will look like this:

    ```azurecli-interactive
    az webapp create --name blankinterestingapp --plan HostedServicePlan --resource-group APPSERVICEGROUP --runtime "DOTNETCORE|2.0"
    ```

5.  On the left side of the portal, click the **Resource groups** link.

6.  In the **Resource groups** blade, locate and select the **APPSERVICEGROUP** *Resource Group* link.

7.  In the **APPSERVICEGROUP** blade, select the **Web App** you most recently created.

8.  In the **Web App** blade, click the **Browse** button at the top of the blade.

9.  Observe the placeholder page provided by Azure App Service.

1. Close the currently running web browser application.

> **Results**: After completing this exercise, you will have used the Azure Cloud Shell to interactively invoke commands using the Azure CLI.

### Exercise 5: Cleanup Subscription

#### Task 1: Open Cloud Shell

1.  At the top of the portal, click the **Cloud Shell** icon to open a new shell instance.

2.  In the **Cloud Shell** command prompt at the bottom of the portal, type in the following command and press **Enter** to list all resource groups in the subscription:

    ```azurecli-interactive
        az group list
    ```

3.  Type in the following command and press **Enter** to view a list of possible CLI commands to *delete a Resource Group*:

    ```azurecli-interactive
        az group delete --help
    ```

#### Task 2: Delete Resource Groups

1.  Type in the following command and press **Enter** to delete the **APPSERVICEGROUP** *Resource Group*:

    ```azurecli-interactive
        az group delete --name APPSERVICEGROUP --no-wait --yes
    ```

1.  Type in the following command and press **Enter** to delete the **VIRTUALMACHINEGROUP** *Resource Group*:

    ```azurecli-interactive
        az group delete --name VIRTUALMACHINEGROUP --no-wait --yes
    ```

3.  Close the **Cloud Shell** prompt at the bottom of the portal.
