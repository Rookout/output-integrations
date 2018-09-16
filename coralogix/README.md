---
title: Coralogix-Rookout Integration
integration_title: Rookout
kind: integration
git_integration_title: Rookout
---

![logo][rookout-image]

## Setup

### Installation

Rookout sends data to Coralogix via a HTTP Webhook.

1. Create Coralogix Account [see their docs](coralogix-docs-url)

2. Setup [Rookout][rookout-url]

3. Log into [Rookout's webapp][rookout-app-url]

1. In the right panel (Rules) click on the menu button

    ![Rule actions menu](screenshots/click_rule_action.png)

1. Click on *Create new template* in order to edit a new rule template

    ![Create new template button](screenshots/click_new_template.png)

1. Copy the Coralogix rule template [available here](coralogix-template.json) into the editor and replace the default rule template.


1. Click the save icon to save the template

    ![Click Save Icon](screenshots/click_save.png)

1. Add the newly created rule to any application as you would normally !

### Configuration

Once you added the rule, you can replace the `url` to another Coralogix endpoint (the default is https://api.coralogix.com/api/v1/logs)
Change the YOUR_PRIVATE_KEY to your private key, and edit the text keys as your wish.

```json
	"operations": [
      {
        "name": "coralogix",
        "target": {
          "url": "https://api.coralogix.com/api/v1/logs",
          "coralogix": {
            "privateKey": "YOUR_PRIVATE_KEY",
            "applicationName": "rook.executable",
            "subsystemName": "rook.platform",
            "computerName": "rook.hostname",
            "IPAddress": "rook.ip"
          },
          "logEntry": {
            "severity": "2",
            "text": "INSERT_TEXT",
            "category": "INSERT_CATEGORY",
            "className": "store.rookout.frame.filename",
            "methodName": "store.rookout.frame.function"
          }
        }
      }
    ]
```

## Troubleshooting
If you have any questions, contact us at support@rookout.com.

## Further Reading
Find out more at [https://docs.rookout.com][rookout-docs]

[rookout-image]: logos/avatars-bot.png
[rookout-url]: https://docs.rookout.com/docs/getting-started.html
[rookout-docs]: https://docs.rookout.com/
[rookout-app-url]: https://app.rookout.com
[coralogix-docs-url]: https://coralogix.com/
