# Rookout + Graylog

The [Rookout] agent can be configured to send notifications arriving from your
application to a [Graylog] input.

## Setup

1. Start by setting up a Graylog environment. You can use your existing setup,
or, for a quick test, you can use the Docker Compose template supplied:

```bash
docker-compose up -d
```

You can access Graylog's management interface on http://localhost:9000 with the
username and password `admin`.

2. Add a new input: On the menu bar, go to `System > Inputs`. From the dropdown,
select the kind of input you would like to set up. Currently, Rookout only
supports `GELF UDP` and press `Launch new input`. Choose a node, a title,
and also which port to use. Click `Save`.

3. On the Rookout management interface, in the Rules pane, from the "Rule Actions"
drop down, select "Create New Template".

4. Copy the contents of rule.json to the template editor. Note the target
parameters on line 38, and the message to log on line 33. You can edit this as
you wish, using data from your app (see general documentation).

5. Select your new template from the "Rule type" drop down, and click next to
the line in the code you wish to use this rule one.

6. Check that the messages have arrived to your Graylog server.

[Graylog]: https://www.graylog.org/
[Rookout]: https://rookout.github.io
