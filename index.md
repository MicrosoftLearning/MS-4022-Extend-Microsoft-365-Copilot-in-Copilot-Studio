---
title: Exercise Instructions
permalink: index.html
layout: home
---

# Exercises

This page lists exercises associated with Microsoft skilling course **MS-4022: Extend Microsoft 365 Copilot in Copilot Studio**.

Related learning path: [Extend Microsoft 365 Copilot in Copilot Studio](https://learn.microsoft.com/training/paths/extend-microsoft-365-copilot-studio/).

**Note**: To complete these exercises, you will need:

- A work or school account with [access to Copilot Studio](https://learn.microsoft.com/microsoft-copilot-studio/requirements-licensing-subscriptions). If you don't already have access to Copilot Studio, depending on the configuration of your Microsoft 365 organization, you may be able to [create a trial account](https://learn.microsoft.com/microsoft-copilot-studio/sign-up-individual).
- A Microsoft 365 Copilot license
- Credentials needed to connect to desired content sources (connectors, APIs, etc.)

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %}
{% for activity in labs  %}
- [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }})
{% endfor %}

