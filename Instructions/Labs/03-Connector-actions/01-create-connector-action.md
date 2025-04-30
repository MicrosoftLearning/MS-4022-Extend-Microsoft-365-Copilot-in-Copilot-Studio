---
lab:
    title: 'Create a connector action'
---

# Create a connector action

In this exercise you will configure a connector action for a declarative agent in Copilot Studio. You'll use the "SharePoint - List folder" connector to retrieve a list of files from a Products folder that contains product support files.

This exercise should take approximately **10** minutes to complete.

## Before you start

This exercise assumes the following:

1. You've already created a **Product Support** declarative agent in Copilot Studio.
1. You have a SharePoint site titled **Product Support** that contains a document library named **Products** containing files with sample product-related data.

## Create a SharePoint connector action

1. In your web browser, navigate to [Copilot Studio](https://www.copilotstudio.microsoft.com) at `https://www.copilotstudio.microsoft.com`.
1. From the **Library** select your **Product Support** agent.
1. Under **actions** select **Add action**.
1. In the **Add action** window, enter `SharePoint` in the **Search** bar. Wait for relevant actions to be displayed in the window.
1. Browse and select the **List Folder SharePoint** connector action.
1. The modal window displays a connection for the SharePoint connector. A green checkmark will be displayed next to the connector when your connection is active. You may select the **...** to view details about the connection.
    ![Screenshot of the SharePoint connection status](../Media/SharePoint-connection.png)
1. Select **Next** when the connection is active. You're taken to the **List folder** page to configure properties for the action.
1. In the **Name** text box, enter `List product support files`.
1. In the **Description** text box, enter `List product support files available in the Products folder`.
1. Confirm that **End user authentication** is set to **User authentication**.
1. Expand the **inputs and outputs** section.
1. Select the **Site Address** input.
1. In the **Value** text box, enter the URL to your **Product Support** SharePoint site in the format `https://DOMAIN.sharepoint.com/sites/ProductSupport` then select **Done**.
1. Select the **File Identifier** input.
1. Set **How will the agent fill this input?** to **Set as a value** from the drop-down then select **Confirm**.
1. In the **Value** text box, enter `Products` then select **Done**.
1. Select the **Add action** button and wait for the SharePoint action to be added to your agent. The action should now be listed in the **Actions** section of your agent's detail page.

## Configure the action

1. From the **Actions** section, select the **List product support files** action to open its details page.
1. Navigate to the **Outputs** tab.
1. For testing purposes, under **Choose how this action's result will be displayed** check the box labelled **Send a message immediately after running the action**. An additional configuration option will be displayed.
1. Select the dropdown under **How do you want to display information to the user?** then select **You create a message**. A text box will be displayed.
1. In the **Message to display** text box, enter `You used the SharePoint connector` then select **Save** at the top of the page.

## Modify the agent's instructions

Let's also update your agent's instructions providing guidance to use the connector action.

1. From the **Details** section of your **Product Support** agent, select **Edit**.
1. In the **Instructions** text box, add the following to the existing instructions text: `When asked about available support resources, use the SharePoint connector to list the files in the Products folder.`
1. Select **Save**.

## Test your agent with the action

1. Expand the **Test your agent** pane on the right side of your agent's detail page.
1. Select the **refresh** button in the test pane to load your agent's latest changes.
1. In the message box, enter `What product support files are available?` then send the message.
1. Notice that your agent responds with the message "You used the SharePoint connector" and then lists the files available in the Products folder.

You've validated that your connector action works as expected within your agent.
