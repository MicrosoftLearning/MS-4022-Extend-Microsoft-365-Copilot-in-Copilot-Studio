---
lab:
    title: '2.1: Create a prompt action'
---

# Create a prompt action

In this exercise you will create a prompt action, test the prompt in Copilot Studio, and test the prompt within a Copilot agent. You'll create a prompt action that helps users turn their raw ideas into organized marketing pitches that follow a specific format and guidelines.

This exercise should take approximately **15** minutes to complete.

## Create a custom prompt in Copilot Studio

1. Open Copilot Studio in your web browser by navigating to [Copilot Studio](https://copilotstudio.microsoft.com) at `https://copilotstudio.microsoft.com`.
1. Select **Tools** from the left hand navigation.
1. Select **New tool**.
1. On the New Tool popup window, select **Prompt**. You're taken to the prompt builder UI. Copilot is available within this window, but we'll define our prompt manually for this exercise.
1. In the textbox at the top of the window, select the auto-generated name and replace it with the name **Marketing Pitch Prompt**.
1. In the **Instructions** text box, enter `Create a marketing pitch for a product based on a `.
1. Place your cursor at the end of the sentence you entered then select **Add content**
1. Select **Text**.
1. In the **Name** field, enter `Draft`.
1.  In the **Sample data** field, enter `The Mighty Mechanical Pencil is new, exciting, and useful. It's not only the first of its kind pencil, but it's fun to use.` then select **Close**.

    ![Screenshot of the prompt builder UI in Copilot Studio showing an input variable being configured with the name "Draft".](../Media/prompt-content-sample-data.png)

## Test and refine your prompt

1. Select **Test** above the instructions box to test the prompt with the sample data you provided.
1. View the output of the test run in the **Model respoonse** section.

Let's refine the prompt to create more structured and consistent output.

1. In the **Instructions** textbox, add the following to the existing instructions to modify the prompt:

    ```The pitch should follow the following Contoso guidelines:
       - Start with a brief hook
       - Describe unique value proposition
       - End with a call-to-action
       - Use an exciting and influential tone
    ```

1. Select **Test** again to retest the prompt.
1. Notice how the response differs.
    ![Screenshot of the custom prompt UI after testing the refined prompt.](../Media/test-prompt-refined.png)
1. Select **Save** to save the prompt.

## (Optional) Add a prompt action to an agent

If you've completed the previous lab and created a declarative agent, you may add this action to your agent and update the agent's instructions to reference the action.

### Add the prompt tool

1. From the sidebar in Copilot Studio, select **Agents**.
1. Select **Microsoft 365 Copilot**.
1. Under **Agents**, select the **Product Support** agent you'd like to add the action to.
1. From the **Tools** section of the page, select **Add tool**.
1. Select the **Prompt** filter.
1. Select the **Marketing Pitch Prompt** tool.
    ![Screenshot of the Add tool window listing the Marketing Pitch Prompt tool.](../Media/add-marketing-pitch-tool.png)
1. Select **Add and configure** and wait for the tool to be added. The tool is now listed in the Product Support agent's **Tools**.
    ![Screenshot of the Product Support agent's Tools section, listing the Marketing Pitch Prompt tool.](../Media/agent-updated-tools.png)

### Update the agent's instructions and starter prompts

Update the agent's instructions to provide guidance for using the prompt.

1. In the **Instructions** text box, add the following to the existing instructions text and then **Save** your changes: `Use the Marketing Pitch Prompt tool to craft pitches for products that follow Contoso guidelines based on users' draft ideas.`
1. In the **Suggested prompts** section, replace the Eagle Air suggested prompt with the following suggested prompt and then **save** your changes: `Marketing Pitch` : `Create a marketing pitch following Contoso guidelines based on the following draft:`.

You've completed the exercise and created a prompt tool for your agent.
