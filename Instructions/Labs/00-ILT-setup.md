---
lab:
  title: ILT Setup
  description: In this exercise, you will access the Microsoft Copilot Studio portal and create an environment to use throughout the remaining labs.
  duration: 10 minutes
  level: 200
  islab: true
  primarytopics:
    - Microsoft 365
    - Microsoft Copilot Studio
---

# Create a Power Platform environment

## Power Platform Admin Center

Before you start the lab exercises, you must create a development environment for you to work in.

1. Open a web browser, navigate to `https://admin.powerplatform.microsoft.com/manage/environments`, and sign in using your credentials for this exercise.

1. If prompted, choose the option to stay signed in.

1. Close any pop-up messages that are displayed.

### Add Dataverse to the default environment

1. Select the ellipses (**...**) for the **Contoso (default)** environment and select **Add Dataverse**.

   ![Add Dataverse to the default environment in the Power Platform Admin center.](../media/add-dataverse.png)

1. Leave all of the default settings and select **Add**.

### Create a new environment

1. In the **Environments** page, select **+ New** to create a new environment with the following settings:

   - **Type**: Developer
   - **Region**: default region
   - **Name**: *Your name*
   - **Environment group**: None
   - **Make this a Managed Environment**: No
   - **Get new features early**: No
   - **Create on behalf**: No

   ![Create an environment in the Power Platform Admin center.](../media/create-environment.png)

1. Select **Next** and in the **Add Dataverse** section:

   - **Language**: English (United States)
   - **Currency**: USD ($)
   - **Deploy sample apps and data**: No

1. Select **Save** and wait until the state of your environment is **Ready** (you can use the **Refresh** button to update the display).

   > [!NOTE]
   > Environment provisioning can take several minutes depending on tenant configuration.

   ![Environment created in the Power Platform Admin center.](../media/environment-created.png)

1. In a new browser tab, navigate to `https://copilotstudio.microsoft.com/` and sign in if prompted.

   > [!NOTE]
   > If you encounter issues to access Copilot Studio, copy the environment id from the new created environment in the Power Platform Admin Center and paste it into the following URL: `https://copilotstudio.microsoft.com/environments/<environment-id>`. Replace `<environment-id>` with the environment id you copied.

1. If prompted, select **Get Started** and keep the default country or region settings.

1. Skip any welcome messages.

1. In the upper right corner of the page, switch environments by using the Environment Selector and select the environment you created.

   ![Select your environment in the Copilot Studio.](../media/select-environment.png)


You now have a Power Platform environment to work in.
