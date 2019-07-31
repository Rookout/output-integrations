---
title: DatadogApi-Rookout Integration
integration_title: Rookout
kind: integration
git_integration_title: Rookout
---

![logo](logos/avatars-bot.png)

## Overview

Collect [custom metrics](https://docs.datadoghq.com/getting_started/custom_metrics/) from your application with a few clicks and send it to DataDog. No need to write code, redeploy or restart your app. [Start a free trial](https://www.rookout.com/trial).
* Enhance monitoring and expedite production debugging with Rookout’s on-demand data collection. 
* Have a new custom metric but you didn’t create the instrumentation to collect it? Not a problem. Rookout can collect custom metrics ad-hoc.
* Datadog Pro customers are allotted 100 custom metrics per host & Enterprise customers are allotted 200 custom metrics per host. More will incur billing charges.

You can find Rookout's integration on [Datadog's integrations page](https://docs.datadoghq.com/integrations/rookout/)

## Setup
### Installation
Rookout uses Datadog Api to send your costume metrics.

1. Log into [Rookout's webapp](https://app.rookout.com)

1. In the right panel (Breakpoints) click on the menu button

    ![Breakpoint actions menu](screenshots/click_rule_action.png)

1. Click on *Create new template* in order to edit a new Breakpoint template

    ![Create new template button](screenshots/click_new_template.png)

1. Copy the Datadog Custom Metric Breakpoint template [available here](rule-template.json) into the editor and replace the default Breakpoint template.

    ![Datadog Custom Metric Breakpoint template](screenshots/datadog_rule_template.png)

1. Click the save icon to save the template

    ![Click Save Icon](screenshots/click_save.png)

1. Add the newly created Breakpoint to any application as you would normally !

### Configuration

You can configure the Breakpoint to use specific actions, every Breakpoint should contain these attributes in the `processing.operations` object:

```json
{
    "name": "datadog",
    "api_key": "<YOUR-API-KEY>",
    "metrics": [
        {
            "metric": "<METRIC-NAME>",
            "points": [
              "<YOUR-INTEGER-VARIABLE>"
            ],
            "tags": [
              "tag1",
              "tag2"
            ],
            "type": "rate"
        }
    ]
}
```

These are the metrics type supported by datadog:

| Metric Type    |    Attributes    |
|:--------------:|:-----------:|
|    count       | value       |
|      gauge     | value       |
|    rate        | value       |
For more information about these types you can see [Dogstatsd documentation](https://docs.datadoghq.com/developers/metrics/)

## Troubleshooting
If you have any questions, contact us at support@rookout.com.

## Further Reading
Find out more at [https://docs.rookout.com/](https://docs.rookout.com/).
