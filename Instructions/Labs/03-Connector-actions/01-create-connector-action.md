---
lab:
    title: '3.1: Create a connector tool'
---

# Create a connector tool

In this exercise, you will configure a connector tool for a declarative agent in Copilot Studio. You'll use the "SharePoint - List folder" connector to retrieve a list of files from a Products folder that contains product support files.

This exercise should take approximately **15** minutes to complete.

## Before you start

This exercise focuses on adding connector tools to an existing agent. This exercise assumes the following:

1. You've already created a **Product Support** declarative agent in Copilot Studio. If you need instructions for creating a declarative agent, see: [Create a declarative agent](../01-Build-your-first-declarative-agent/01-create-declarative-agent.md).
1. You have a SharePoint site titled **Product Support** that contains a document library named **Products** containing files with sample product-related data. For instructions, see the section titled **Before you start** within the exercise: [Add custom knowledge](../01-Build-your-first-declarative-agent/02-add-custom-knowledge.md).

## Create a SharePoint connector tool from a prebuilt connector

Create a connector tool using the SharePoint List Folder prebuilt connector and add it to the agent.

1. In your web browser, navigate to [Copilot Studio](https://www.copilotstudio.microsoft.com) at `https://www.copilotstudio.microsoft.com`.
1. In the sidebar, select **Agents**.
1. Select **Microsoft 365 Copilot**.
1. Under **Agents**, select your **Product Support** agent.
1. Under **Tools** select **Add tool**.
1. In the **Add tool** window, enter `SharePoint` in the **Search** bar. Wait for relevant connectors to be displayed in the window.
1. Browse and select the **List Folder** SharePoint connector.
1. The modal window displays a connection for the SharePoint connector. A green checkmark will be displayed next to the connector when your connection is active. You may select the **...** to view details about the connection. If the status is `Not connected`, select the dropdown next to **Not connected** and select **Create new connection**.
    ![Screenshot of the SharePoint connection status](../Media/SharePoint-connection.png)
1. On the **Connect to SharePoint** page, select **Connect directly (cloud services)** then select **Create**.
1. You will be prompted to sign in. Sign in using the M365 account you're using for the exercise.
1. On the **Add tool** page, after a connection is established, select **Add to agent** to add the tool to your agent.

## Configure the connector tool for your agent

Configure the properties of the connector tool for the agent.

1. From the **Product Support** agent page, under **Tools** select the **List folder - connector** tool you added in the previous section.
1. In the **Name** text box, enter `List product support files`.
1. In the **Description** text box, enter `List product support files available in the Products folder`.
1. Select the toggle next to **Additional details** to reveal additional properties.
1. In the **Description** text box in the **Additional details** section, enter `Please log in to access the Product Support SharePoint."
1. In the **Inputs** section,  locate the **Site Address** input. In the **Value** text box, enter the URL to your **Product Support** SharePoint site in the format `https://DOMAIN.sharepoint.com/sites/ProductSupport` then select **Done**.
1. Next, locate the **File Identifier** input. Set the **Fill using** field to **Custom value** from the drop-down.
1. In the **Value** text box for **File Identifier**, enter `Products` then select **Done**.
1. Select **Save** at the top of the page to save your changes.
   
## Modify the agent's instructions

Let's also update your agent's instructions, providing guidance to the agent for how to use the connector tool.

1. From the **Details** section of your **Product Support** agent, select **Edit**.
1. In the **Instructions** text box, add the following to the existing instructions text: `When asked about available support resources, use the SharePoint connector to list the files in the Products folder.`
1. Select **Save**.

## Test your agent with the tool

1. Expand the **Test your agent** pane on the right side of your agent's detail page.
1. Select the **refresh** button in the test pane to load your agent's latest changes.
1. In the message box, enter `What product support files are available?` then send the message.
1. Notice that your agent responds with the message "You used the SharePoint connector" and then lists the files available in the Products folder.

You've validated that your connector tool works as expected within your agent.
