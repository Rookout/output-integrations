# Rookout + Sentry

The [Rookout] agent can be configured to send notifications arriving from your
application to a [Sentry] project.

## Setup

1. Start by making sure you have a Sentry project DSN path (also referred as Client Key) in order to use this rule.
If you do not already have a key, you can fetch it from Settings > sentry > PROJECT_NAME > Client Keys (DSN)

1. On the Rookout management interface, in the Rules pane, from the "Rule Actions"
drop down, select "Create New Template".

1. Copy and replace the contents of rule.json to the template editor.

1. Paste your Sentry DSN path you generated on line 12 instead of `YOUR_DSN`.

1. You can edit template configuration as you wish to select where to send the alerts and to add a custom message or remove unnecessary variables.

    | Line | Attribute |                     Description                     |
    |:----:|:---------:|:---------------------------------------------------:|
    |   7  |   format  |   Template describing what info the log will send   |
    |  13  |  tags     |   Optional tags that will appear in your logs		 |

1. Save the template by clicking the save icon next to its title in the file explorer

1. Select your new template from the "Rule type" drop down, and click next to
the line in the code you wish to use this rule one.

1. Check that the messages have arrived to your Sentry.

__For more information on Rule Scripting [check out our documentation](https://docs.rookout.com/docs/rules.html)__

[Sentry]: https://sentry.io/
[Rookout]: https://docs.rookout.com/
