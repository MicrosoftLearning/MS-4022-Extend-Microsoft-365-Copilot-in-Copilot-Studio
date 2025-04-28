---
lab:
    title: 'Add custom knowledge'
---

# Add custom knowledge <!-- match title in metadata above (and Learn Exercise unit and ILT slide)-->

In this exercise you will update the declarative agent you created in the previous exercise with custom instructions and grounding data. This exercise assumes you have a SharePoint site containing sample product files.

This exercise should take approximately **10** minutes to complete.

## Configure your agent with custom knowledge

First, configure your agent to use the SharePoint site data.

### Add SharePoint URL

> **Note**: Copilot Studio agents access documents on behalf of the user. Your agent will only be able to get answers and content from documents your end users have access to.

**TODO: Insert steps**


### Update custom instructions

**TODO: Insert steps**

1. Select **edit**.
2. In the **Instructions** text box, add the following to the existing instructions for your agent: `You will use documents from the Products folder in SharePoint as your source of information. If you can't find the necessary information, you should suggest that the agent should reach out to the team responsible for further assistance. Your responses should be concise and always include a cited source.`.
3. Select **Save**.
4. Select **Publish** to publish the changes to your agent.

**TODO: complete republishing steps**

### Test your agent in Microsoft 365 Copilot

Let's test the grounding data.

1. In the message box, enter **Tell me about Eagle Air** and send the message.
2. Wait for the response. Notice that the response contains information about the Eagle Air drone. The response contains citations and references to the Eagle Air document stored in OneDrive.

:::image type="content" source="../media/test-product-info.png" alt-text="Screenshot of Microsoft Edge showing Microsoft 365 Copilot. A response from the Product support agent is displayed showing product details for Eagle Air. A document is cited and referenced in the response as the source of grounding data." lightbox="../media/test-product-info.png":::

Let's try a few more prompts:

1. In the message box, enter **Recommend a product suitable for a farmer** and send the message.
1. Wait for the response. Notice that the response contains information about the Eagle Air and some extra context as to why the Eagle Air is recommended. The response contains citations and references to the Eagle Air document stored in OneDrive.

    :::image type="content" source="../media/test-product-recommendation.png" alt-text="Screenshot of Microsoft Edge showing Microsoft 365 Copilot. A response from the Product support agent is displayed showing product details for Eagle Air as a product recommendation. A document is cited and referenced in the response as the source of grounding data." lightbox="../media/test-product-recommendation.png":::

1. In the message box, enter **Explain why the Eagle Air is more suitable than Contoso Quad** and send the message.
1. Wait for the response. Notice that the response explains in more detail why the Eagle Air is more suitable than the Contoso Quad for use by farmers.

    :::image type="content" source="../media/test-product-explanation.png" alt-text="Screenshot of Microsoft Edge showing Microsoft 365 Copilot. A response from the Product support agent is displayed with an explanation of why the Eagle is air is more suitable for use by farmers." lightbox="../media/test-product-explanation.png":::

Finally, let's test the fallback response by asking a question that the agent can't answer:

1. In the message box, enter **When was Mark8 released?** and send the message.
1. Wait for the response. Notice that the response suggests that the agent should reach out to the team responsible for further assistance as defined in the instructions.

:::image type="content" source="../media/test-fallback.png" alt-text="Screenshot of Microsoft Edge showing Microsoft 365 Copilot. A response from the Product support agent is displayed. The agent can't answer the question so makes a suggestion to find information from another source." lightbox="../media/test-fallback.png":::
