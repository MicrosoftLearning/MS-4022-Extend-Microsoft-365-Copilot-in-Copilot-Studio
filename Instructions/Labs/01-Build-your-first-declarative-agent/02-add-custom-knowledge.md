---
lab:
    title: '1.2: Add custom knowledge'
---

# Add custom knowledge

In this exercise you will update the declarative agent you created in the previous exercise with custom instructions and grounding data. This exercise assumes you have a SharePoint site with a document library named "Products" that contains sample product files.

This exercise should take approximately **10** minutes to complete.

## Configure your agent with custom knowledge

### Add SharePoint URL

First, configure your agent to use the SharePoint site data.

1. From your Product Support agent's overview page in Copilot Studio, select **Add knowledge** in the **Knowledge** section.

    ![Screenshot of Copilot Studio in Microsoft Edge highlighting the Add knowledge button for the Product support agent.](../Media/product-support-add-knowledge.png)

1. On the **Add knowledge** page of the wizard that opens, select **SharePoint**.
1. In the text box, paste the URL of your **Products** SharePoint library then select **Add**. This should be in the format: `https://DOMAIN.sharepoint.com/sites/ProductSupport/Products`.

1. Select **Add** on the **Add SharePoint** window then wait for the knowledge source to be added to the agent. This may take a minute or two.
1. Notice that the **Products** library is listed under the **Knowledge** section of the agent's overview information.

> **Note**: Copilot Studio agents access documents on behalf of the user. Your agent will only be able to get answers and content from documents your end users have access to.

### Update custom instructions

Next, update the agent's instructions to describe how the agent should use the knowledge source.

1. From the agent's overview page in Copilot Studio, select **Edit** within the **Details** section.
1. Update the contents of the **Instructions** text box to the following: `You are an agent tasked with answering questions about Contoso Electronics products. Start every response by enthusiastically thanking the user for their question or comment, then respond to their question or comment. You will use documents from the Products folder in SharePoint as your source of information. If you can't find the necessary information, you should suggest that the agent should reach out to the team responsible for further assistance. Your responses should be concise and always include a cited source.`
1. Select **Save** in the **Details** section.

## Test your agent in Copilot Studio

Let's test your agent's ability to use the custom knowledge source.

1. From the **Test your agent** pane in your agent's overview page in Copilot Studio, select the **refresh** button to refresh the test pane and load your agent's latest changes.
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
