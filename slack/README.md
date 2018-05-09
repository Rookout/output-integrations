# Rookout + Slack

The [Rookout] agent can be configured to send notifications arriving from your
application to a [Slack] channel.

## Setup

1. Start by making sure you have a Slack token in order to use this rule.
If you do not already have a token, you can generate one here by clicking on `Create Token`:
[https://api.slack.com/custom-integrations/legacy-tokens](https://api.slack.com/custom-integrations/legacy-tokens)

1. On the Rookout management interface, in the Rules pane, from the "Rule Actions"
drop down, select "Create New Template".

1. Copy and replace the contents of rule.json to the template editor.

1. Paste your Slack token you generated on line 14 instead of `YOUR_TOKEN`.

1. You can edit template configuration as you wish to select where to send the alerts and to add a custom message or remove unnecessary variables.

    | Line | Attribute |                     Description                     |
    |:----:|:---------:|:---------------------------------------------------:|
    |   7  |   format  |   Template describing what info the log will send   |
    |  12  |  channel  | Slack channel name you want the messages to be sent |

1. Save the template by clicking the save icon next to its title in the file explorer

1. Select your new template from the "Rule type" drop down, and click next to
the line in the code you wish to use this rule one.

1. Check that the messages have arrived to your Slack channel.

__For more information on Rule Scripting (check out our documentation)[https://rookout.github.io/scripts/index.md]__

[Slack]: https://slack.com/
[Rookout]: https://rookout.github.io
