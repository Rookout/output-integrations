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

1. In the right panel (Breakpoints) click on the menu button

    ![Breakpoint actions menu](screenshots/click_rule_action.png)

1. Click on *Create new template* in order to edit a new Breakpoint template

    ![Create new template button](screenshots/click_new_template.png)

1. Copy the Elastic Breakpoint template [available here](rule-template.json) into the editor and replace the default Breakpoint template.


1. Click the save icon to save the template

    ![Click Save Icon](screenshots/click_save.png)

1. Add the newly created Breakpoint to any application as you would normally !

### Configuration
Once you added the Breakpoint, you can replace the `hosts` to one or more Elastic hosts
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
          "locals": "store.rookout.frame.locals",
          "variables": "store.rookout.variables"
        }
      }
    ]
```

#### TLS settings (optional)
```json
"operations": [
      {
        "name": "elastic",
        "target": {
          "hosts": [
            "https://elastic:9200"
          ],
          "tlsRootCAFile": "..",
          "tlsClientCertFile": "..",
          "tlsClientKeyFile": ".."
        },
...
```

`tlsRootCAFile` - Path to PEM-encoded file containing Root CAs.
`tlsClientCertFile` - Path to PEM-encoded certificate for client-side TLS
`tlsClientKeyFile` - Path to PEM-encoded key for client-side TLS

All paths are to local files on the controller system. Client-side TLS and custom root
certificates are only supported in on-premises deployments.


## Troubleshooting
If you have any questions, contact us at support@rookout.com.

## Further Reading
Find out more at [https://docs.rookout.com][rookout-docs]

[rookout-image]: logos/avatars-bot.png
[rookout-url]: https://docs.rookout.com/docs/getting-started.html
[rookout-docs]: https://docs.rookout.com/
[rookout-app-url]: https://app.rookout.com
