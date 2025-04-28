---
lab:
    title: 'Create a declarative agent'
---

# Create a declarative agent

In this exercise you will create a declarative agent using generative AI, refine the instructions, publish the agent to Microsoft 365, and test the agent in Microsoft 365 Copilot.

This exercise should take approximately **20** minutes to complete.

## Before you start

<!--
Add steps to get the learner to the starting point" for the exercise.
This might be cloning the repo and running a script or performing some manual steps.
Only include this section if its necessary to do some pre-exercise setup AND the same setup steps are required for self-paced (on Learn) and managed (in hosted ILT lab profiles) scenarios. Otherwise delete this section.
If self-paced /ILT-specific setup steps are required, include them in the Learn "Exercise" unit from where they open this exercise and in the Skillable lab profile instructions before this markdown file is imported.
 -->

Before you can start this exercise, you will need to...

1. Step 1
1. Step 2
1. etc.

# Create a declarative agent using generative AI

Start by creating a new declarative agent in Copilot Studio. Use generative AI to draft the instructions and properties for the agent.

1. Navigate to [Microsoft Copilot Studio](https://copilotstudio.microsoft.com/) at `https://copilotstudio.microsoft.com`.
1. Sign in using a work or school account where you have permission to create in Copilot Studio.
1. If prompted on the **Welcome to Microsoft Copilot Studio** page, select your country/region and then select **Get Started**.
1. On the **Welcome to Copilot Studio!** popup, select **Skip**.
1. The **Create an agent** wizard may open. This wizard helps you set up a *custom* agent.  Select **...** then select **Cancel agent creation** to exit this wizard.  Select **Leave** to confirm.
1. Navigate to **Agents** in the left side navigation panel.
1. Select **Microsoft 365 Copilot** from the list of agents.
1. On the **Microsoft 365 Copilot** agent page within the **Agents** card, select **Add**. You're sent to the conversational authoring experience where you can describe the agent you'd like to build.

    > [!NOTE]
    > Skip over the conversational interface at any time, by choosing **Skip to configure**.

1. You're asked to describe what you'd like your agent to do.  In the **Type your message** text box in the conversational interface, enter the following:

    ```md
    Help answer customer queries about Contoso Electronics products.
    ```

1. Select **enter** or **send** to send your message.
1. If prompted to suggest a name for your agent, enter `Product support` and send your message.
1. If prompted to provide instructions for your agent, enter the following and send your message:

    ```md
    Start every response by enthusiastically letting the user know that they've created a declarative agent. Then, answer the questions and help the user.
    ```

1. Select **Skip to configure** at the top of the conversational interface to view the agent's overview page and review what the generative AI configured so far.

## Configure the agent and define instructions

Next, update the agent's properties and metadata manually.

1. Review the **Name** that the generative AI wizard defined for your agent. Update the name to ensure it is `Product Support`.
1. Update the **description** property to `Product support agent that can help answer customer queries about Contoso Electronics products`.
1. In the **Instructions** text box, enter:
  
    ```md
        You are a declarative agent and were created with Copilot Studio.  Start every response and answer to the user with "You created a declarative agent!\n\n" and then answer the questions and help the user.
    ```

1. Select **Create** at the top of the page to create the agent.  You are taken to the agent's overview page.

## Test the agent in Copilot Studio

Next, test the behavior of your agent in the test pane within Copilot Studio before publishing to Microsoft 365 Copilot.

1. From the **Product Support** agent overview page, note in the **Publish details** section that the agent is not yet published.
1. If the **Test your agent** pane is not displayed to the right of the agent overview information, select the **Test** button next to the Publish button to open the test pane.
1. In the text box, enter `What can you do?` and submit your message.
1. Wait for the response. Notice how the response starts with the text "You created a declarative agent!" as instructed in the instructions you defined for the agent earlier.

    Also notice that the agent currently has instructions but does not yet have any custom knowledge sources or actions. You haven't configured the agent to answer questions about Contoso products yet. You'll do this in the next exercise.

    > [!NOTE]
    > If you need to edit your agent, close the test pane and select **edit** in the **Details** section of the agent overview page. Before testing again, select the **refresh** button inside of the test pane to load the latest changes.

## Publish the agent to Microsoft 365 Copilot

Next, publish your declarative agent to Microsoft 365 Copilot. From the **Product Support** agent overview page:

1. Select the **Publish** button. You're prompted to enter information about your agent that will be displayed to users in Microsoft 365 Copilot and Microsoft Teams.

    > [!NOTE]
    > The information on this form is used to populate the catalog entry in your organization's Office and Teams Catalogs and the Microsoft Admin Center Integrated Apps list. It isn't used by the Microsoft 365 Copilot language model.

1. In the **Short description** text box enter `Product support agent that can help answer customer queries about Contoso Electronics products`.
1. Accept the default suggestions for the remaining fields.
1. Select **Publish**.
1. Wait for the agent to be published.  Do not close the modal window during publishing. This may take a few minutes.

    > [!NOTE]
    > When you select Publish, a bot resource is provisioned in your tenant's Microsoft Entra ID environment, corresponding to your agent. The resource allows users to interact with the agent in Microsoft Teams.

1. Once the agent is published, the **Availability options** window appears.
1. Under **Share link** select **Copy** to copy the share link for your agent.
1. Open a new tab in your web browser, paste the share link into the URL bar, then select **enter**. A modal window appears with an overview of your agent. This displays the user-facing information you provided about your agent during publishing, as well as the permissions required by your agent.
1. Select **Add** to add your agent to Microsoft 365 Copilot.
1. Wait for your agent to be added. Your agent is launched in Microsoft 365 Copilot. 

## Test the agent in Microsoft 365 Copilot

Next, let’s run the declarative agent in Microsoft 365 Copilot and validate its functionality in both the **immersive** and **in-context** experiences.

Following the previous steps, you are currently in the **immersive** agent experience. Notice in the **Agents** pane to the right that  **Product Support** is selected as the agent you are currently chatting directly with.

1. In the text box, enter `What can you do?` and submit your message.
1. Send the message and wait for the response. Notice how the response starts with the text "You created a declarative agent!" as defined in the instructions.

    Continuing in the browser, let’s test the **in-context** experience.
2. Above the **Agents** pane to the right of the chat window, select **Copilot** to exit your immersive chat with the **Product Support** agent and chat with Microsoft 365 Copilot.
3. In the message box enter the <kbd>@</kbd> symbol. The flyout appears with a list of available agents.

    :::image type="content" source="../Media/test-in-context-agent-flyout.png" alt-text="Screenshot of Microsoft Edge showing the agent flyout in Microsoft 365 Copilot. The Product support agent is highlighted." lightbox="../Media/test-in-context-agent-flyout.png":::

5. In the flyout, select **Product support**. Notice the status message above the message box. It displays **Chatting with Product support**, which signifies that you're using the in-context experience of the agent.

    :::image type="content" source="../Media/test-in-context-agent.png" alt-text="Screenshot of Microsoft Edge showing Microsoft 365 Copilot. The status message 'Chatting with Product support' is highlighted." lightbox="../Media/test-in-context-agent.png":::

6. In the text box, enter `What can you do?` and submit your message.

    :::image type="content" source="../Media/test-in-context-message.png" alt-text="Screenshot of Microsoft Edge showing Microsoft 365 Copilot. The text 'What can you do?' is highlighted in the message box." lightbox="../Media/test-in-context-message.png":::

7. Wait for the response. Notice how the response starts with the text "You created a declarative agent!" as defined in the instructions.

    :::image type="content" source="../Media/test-in-context-response.png" alt-text="Screenshot of Microsoft Edge showing Microsoft 365 Copilot. A response from the Product support agent is displayed. " lightbox="../Media/test-in-context-response.png":::

8. To exit the in-context experience, select the (X) in the status message. Notice the status message is removed and a message is displayed in the chat window that indicates that you're no longer chatting with the agent.

    :::image type="content" source="../Media/test-in-context-exit.png" alt-text="Screenshot of Microsoft Edge showing Microsoft 365 Copilot. The cross icon in the agent status message is highlighted." lightbox="../Media/test-in-context-exit.png":::

    :::image type="content" source="../Media/test-in-context-exit-confirm.png" alt-text="Screenshot of Microsoft Edge showing Microsoft 365 Copilot. The message confirming that the declarative agent is no responding is highlighted." lightbox="../Media/test-in-context-exit-confirm.png":::



    :::image type="content" source="../Media/test-immersive-response.png" alt-text="Screenshot of Microsoft Edge showing Microsoft 365 Copilot. A response from the Product support agent is displayed." lightbox="../Media/test-immersive-response.png":::

