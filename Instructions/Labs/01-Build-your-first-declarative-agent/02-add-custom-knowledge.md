---
lab:
    title: '1.2: Add custom knowledge'
---

# Add custom knowledge

In this exercise you will update the declarative agent you created in the previous exercise with custom instructions and grounding data. 

This exercise should take approximately **20** minutes to complete.

## Before you start

Before you can start this exercise, you will need to upload the product-related documents to Microsoft 365 that the declarative agent will use as grounding data. Complete the steps below to prepare for the exercise.

> [!NOTE]
> When you upload documents to a new SharePoint Online site, there's a delay before the documents are indexed and available for use by Copilot. If you wish to test your agent immediately, then upload the documents to an **existing** site. The documents will be indexed and available for use by the agent without delay. If you choose to use a new SharePoint Online site, the documents may take longer to be indexed and available for use by Copilot.
>
> **The instructions below guide you through uploading the documents to a new site**. If you'd like to use an existing site, start with the section labeled **Upload sample data** and use your existing library in place of the **Products** library.

### Download the sample data

1. In a web browser, navigate to the course's [GitHub repo](https://github.com/MicrosoftLearning/MS-4022-Extend-Microsoft-365-Copilot-in-Copilot-Studio/blob/master/Allfiles/Products.zip).
1. Select the **download raw file** button to download **Products.zip**.

    ![Screenshot of Microsoft Edge highlighting the download raw file button in GitHub.](../Media/download-raw-file.png)

1. **Open** the downloaded folder and select **Extract all** to extract the contents to a new folder on your machine named `Products` that you can access later.

### Create a SharePoint site

1. In your web browser, navigate to [https://m365.cloud.microsoft](https://m365.cloud.microsoft/chat) and **sign in** with the Microsoft 365 account you're using for this lab. 
1. In the left-hand menu, select **Apps** (grid icon) and then "All apps" to open the menu of Microsoft 365 apps.
    ![Screenshot of the M365 apps button in Copilot Chat.](../Media/apps-icon.png)
1. Select **SharePoint** from the catalog of apps.
1. From the left-hand menu, select **Create site**.
1. Select **Team site** as the type of site.
1. On the **Select a template** page, select **Standard team**.
1. On the **Preview** page, select **Use template**.
1. On the **Give your site a name** page, enter `Product support` then select **Next**.
1. On the next configuration page, change the **Privacy settings** to **Public**.
1. Select **Create site**. Creation of the site may take a few moments before the **Finish** button is activated.
1. Select **Finish**. You're navigated to your new SharePoint site in the browser.

### Create a document library

1. From the **Product support** SharePoint site, select the **New** button at the top of the page then select **Document library**.
1. On the **Create a new document library** page, select **Blank library**.
1. In the **Name** field, enter `Products` then select **Create**. You're navigated to the new document library.

### Upload sample data

1. From the **Products** library, select the **Upload** button then select **Files**.
1. Navigate to the folder on your computer where you saved the sample files you downloaded in an earlier step.
1. **Select all** of the files in your local Products folder and then select **Open** to upload them to SharePoint.
1. Wait for the upload to complete. The files will now appear in the **Products** library in SharePoint.

### Copy the SharePoint URL

Next, copy the direct URL to the site for use when configuring your agent's knowledge.

1. From the **Products** library page in SharePoint, select the **Settings** icon in the top right and choose **Library settings** then **More library settings**.
1. Locate the **Web address** property. Your **SharePoint site URL** is the portion of the Web address that is in the format `https://DOMAIN.sharepoint.com/sites/SITE_NAME/LIBRARY_NAME`. Your URL should be in the format `https://DOMAIN.sharepoint.com/sites/ProductSupport/Products`, where DOMAIN is your Microsoft 365 tenant domain.
1. **Copy** your SharePoint site URL and save it for use in upcoming lab steps. Do not include any portion of the URL that comes after "/Products".

## Configure your agent with custom knowledge

Add the SharePoint URL to your agent as a grounding  knowledge source.

### Add SharePoint URL

1. In a web browser, navigate to [Microsoft Copilot Studio](https://copilotstudio.microsoft.com/) at `https://copilotstudio.microsoft.com`.
1. Select **Agents**.
1. Select **Copilot for Microsoft 365**.
1. Select your **Product Support** agent.
1. From the **Knowledge** section of the agent overview page, select **Add Knowledge**.
1. On the **Add knowledge** page of the wizard that opens, select **SharePoint**.
1. In the text box, paste the URL of your **Products** SharePoint library then select **Add**. This should be in the format: `https://DOMAIN.sharepoint.com/sites/ProductSupport/Products`.

1. Select **Add to agent** then wait for the knowledge source to be added to the agent. This may take a minute.
1. Notice that the **Products** library is listed under the **Knowledge** section of the agent's overview information.
    ![Screenshot of the Knowledge section of the Product Support agent, showing the Products library added to the agent.](../Media/agent-knowledge-products.png)

    > **Note**: Copilot Studio agents access documents on behalf of the user. Your agent will only be able to get answers and content from documents your end users have access to.

### Update custom instructions

Next, update the agent's instructions to describe how the agent should use the knowledge source.

1. From the agent's overview page in Copilot Studio, select **Edit** within the **Details** section.
1. Replace the contents of the **Instructions** text box with the following: `You are an agent tasked with answering questions about Contoso Electronics products. Start every response by enthusiastically thanking the user for their question or comment, then respond to their question or comment. You will use documents from the Products folder in SharePoint as your source of information. If you can't find the necessary information, you should suggest that the agent should reach out to the team responsible for further assistance. Your responses should be concise and always include a cited source.`
1. Select **Save** in the **Details** section.

## Test your agent in Copilot Studio

Finally, test your agent's ability to use the custom knowledge source.

1. From the **Test your agent** pane in your agent's overview page in Copilot Studio, select the **Start new test session** button to refresh the test pane.
1. In the text box for the test conversation, enter `Tell me about Eagle Air` and send the message.
1. Wait for the response. Notice that the response contains information about the Eagle Air drone. The response contains citations and references to the Eagle Air document stored in SharePoint.

Let's try a few more prompts:

1. In the message box, enter `Recommend a product suitable for a farmer` and send the message.
1. Wait for the response. Notice that the response contains information about the Eagle Air and some extra context as to why the Eagle Air is recommended. The response contains citations and references to the Eagle Air document stored in OneDrive.
1. In the message box, enter `Explain why the Eagle Air is more suitable than Contoso Quad` and send the message.
1. Wait for the response. Notice that the response explains in more detail why the Eagle Air is more suitable than the Contoso Quad for use by farmers.

Finally, let's test the fallback response by asking a question that the agent can't answer:

1. In the message box, enter `When was Mark8 released?` and send the message.
1. Wait for the response. Notice that the response suggests that the agent should reach out to the team responsible for further assistance as defined in the instructions.
    ![Screenshot of the agent's response in the test pane.](../Media/test-agent-knowledge.png)
