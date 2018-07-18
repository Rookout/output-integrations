---
title: Elastic-Rookout Integration
integration_title: Rookout
kind: integration
git_integration_title: Rookout
---

![logo][rookout-image]

## Setup

### Installation

Rookout sends data to Elastic.

1. Setup [Rookout][rookout-url]

1. Log into [Rookout's webapp][rookout-app-url]

1. In the right panel (Rules) click on the menu button

    ![Rule actions menu](screenshots/click_rule_action.png)

1. Click on *Create new template* in order to edit a new rule template

    ![Create new template button](screenshots/click_new_template.png)

1. Copy the Elastic rule template [available here](rule-template.json) into the editor and replace the default rule template.


1. Click the save icon to save the template

    ![Click Save Icon](screenshots/click_save.png)

1. Add the newly created rule to any application as you would normally !

### Configuration

Once you added the rule, you can replace the `hosts` to one or more Elastic hosts
Change the `items` dictionary to output any information that you need to send

```json
"operations": [
      {
        "name": "elastic",
        "target": {
          "hosts": [
            "elastic"
          ]
        },
        "index": "rookout",
        "type": "frame_dump",
        "items": {
          "function": "store.rookout.frame.function",
          "filename": "store.rookout.frame.filename",
          "line": "store.rookout.frame.line",
          "user": "store.rookout.frame.locals.self.user",
          "user_ip": "store.rookout.frame.locals.self.user_ip",
          "forum": "store.rookout.frame.locals.self.forum",
          "topic": "store.rookout.frame.locals.self.topic"
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
