# Rookout + Text File

[Rookout] can be configured to send notifications arriving from your application to a text file.
 The text file will be located where [Rookout ETL Agent](https://docs.rookout.com/docs/agent-setup.html) is running.

## Setup

1. On the Rookout management interface, in the Breakpoints pane, from the "Breakpoint Actions"
drop down, select "Create New Template".

1. Copy and replace the contents of rule.json to the template editor.
    The relevant part is the processing namespace where we added a `text_file` operation:
```json
"processing": {
    "operations": [
        {
        "name": "format",
        "path": "temp.message",
        "format": "LOG: {agent.ip}: {store.rookout.frame.filename}@{store.rookout.frame.line}-{store.rookout.frame.function}"
        },
        {
        "name": "text_file",
        "target": {
            "path": "/var/log/rookout_log.txt",
            "buffering": 0
        },
        "message": "temp.message"
        }
    ]
}
```

1. You can edit template configuration as you wish to select where to write the log and to choose what is the message.

    | Line | Attribute |                     Description                     |
    |:----:|:---------:|:---------------------------------------------------:|
    |  57  |   path  |   Absolute path of the log file. The log file itself will be created but the folders must exist.   |
    |  52  |  format  | What message will be written to the log file |

1. Save the template by clicking the save icon next to its title in the file explorer

1. Select your new template from the "Breakpoint type" drop down, and click next to
the line in the code you wish to use this Breakpoint.

1. Check that the messages have been written to the file.

__For more information on Breakpoint Scripting [check out our documentation](https://docs.rookout.com/docs/rules.html)__

[Rookout]: https://docs.rookout.com/
