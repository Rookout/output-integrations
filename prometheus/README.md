# Rookout + Prometheus

[Rookout] can be configured to send notifications arriving from your application to a [Prometheus] project.

## Setup

1. Start by making sure you have a functional prometheus server.

2. Setup [Rookout](https://docs.rookout.com/)

3. Log into [Rookout's webapp](https://app.rookout.com/)

1. In the right panel (Breakpoint) click on the menu button

    ![Breakpoint actions menu](screenshots/click_rule_action.png)

1. Click on *Create new template* in order to edit a new Breakpoint template

    ![Create new template button](screenshots/click_new_template.png)

1. Copy the Prometheus Breakpoint template [available here](rule-template.json) into the editor and replace the default Breakpoint template.

1. Click the save icon to save the template

    ![Click Save Icon](screenshots/click_save.png)
	
## Configuration

Once you added the Breakpoint, you can replace the `hosts` to one or more Prometheus hosts
Change the `items` dictionary to output any information that you need to send

```json
"operations": [
        {
		"url": "YOUR_URL",
		"metrics": {
		  "yourInteger": "store.rookout.frame.yourInteger",
		  "yourFloat": "store.rookout.frame.yourFloat"
		},
		"counters":["my_counter", "another_counter"],
		"job": "prometheus_job",
		"name": "prometheus"
	}
]
```

1. Check that the messages have arrived to your Prometheus.


## Troubleshooting
If you have any questions, contact us at support@rookout.com.

## Further Reading
Find out more in our [Documentation](https://docs.rookout.com)

__For more information on Breakpoint Scripting [check out our documentation breakpoint scripting section](https://docs.rookout.com/docs/rules.html)__

[Prometheus]: https://prometheus.io/
[Rookout]: https://docs.rookout.com/
