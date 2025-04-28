---
lab:
    title: 'Add custom knowledge'
---
<!--
Edit the metadata above to manage the list of exercises in the home page of the GitHub site that gets generated.
You can delete the module and edit index.md in the root of the repo to customize the display so that only the exercises are listed
To enable GitHub page publishing, edit the Page settings for the repo and publish from the main branch
-->

# Add custom knowledge <!-- match title in metadata above (and Learn Exercise unit and ILT slide)-->

In this exercise you will update the declarative agent you created in the previous exercise with custom instructions and grounding data.

This exercise should take approximately **10** minutes to complete.

## Before you start

<!--
Add steps to get the learner to the starting point" for the exercise.
This might be cloning the repo and running a script or performing some manual steps.
Only include this section if its necessary to do some pre-exercise setup AND the same setup steps are required for self-paced (on Learn) and managed (in hosted ILT lab profiles) scenarios. Otherwise delete this section.
If self-paced /ILT-specific setup steps are required, include them in the Learn "Exercise" unit from where they open this exercise and in the Skillable lab profile instructions before this markdown file is imported.
 -->

## Configure your agent with custom knowledge

First, configure your agent to use the SharePoint site data.

### Add SharePoint URL

> **Note**: Copilot Studio agents access documents on behalf of the user. Your agent will only be able to get answers and content from documents your end users have access to.

### Update custom instructions

**TODO: Insert steps**

## Update custom instructions

Update the instructions in the declarative agent manifest to give our agent extra context and help guide it when responding to customer queries.

In Visual Studio Code:

1. Open the **appPackage/instruction.txt** file and update the contents with:

    ```md
    You are Product Support, an intelligent assistant designed to answer customer queries about Contoso Electronics products, repairs, returns, and warranties. You will use documents from the Products folder in SharePoint as your source of information. If you can't find the necessary information, you should suggest that the agent should reach out to the team responsible for further assistance. Your responses should be concise and always include a cited source.
    ```

1. Save your changes.

## Test the behavior of your agent

Test your declarative agent in Copilot Studio and validate the results.

### Test the instructions

Continuing in the web browser:

1. In **Microsoft 365 Copilot**, select the icon in the top right to **expand the Copilot side panel**.
1. Find **Product support** in the list of agents and select it to enter the immersive experience to chat directly with the agent.
1. Select the sample prompt with the title **Learn more** and send the message.
2. Wait for the response. Notice how the response is different from the previous instructions and reflects the new instructions, no longer starting its response with the phrase from the previous instructions.

:::image type="content" source="../media/test-custom-instructions.png" alt-text="Screenshot of Microsoft Edge showing Microsoft 365 Copilot. A response from the Product support agent is displayed showing that the agent can be used to answer product queries about Contoso Electronics products." lightbox="../media/test-custom-instructions.png":::

### Test the grounding data

Next, let's test the grounding data.

1. In the message box, enter **Tell me about Eagle Air** and send the message.
1. Wait for the response. Notice that the response contains information about the Eagle Air drone. The response contains citations and references to the Eagle Air document stored in OneDrive.

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
