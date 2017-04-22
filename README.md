# Python3 script to display a PC's today uptime

For Elementary OS and Ubuntu.

Displays today's uptime with Gtk's AppIndicator3 library and displays a warning icon once a certain amount of hours (by default 5) are exceeded.

The warning icon is the `clock-alert` icon with more padding from https://materialdesignicons.com/

## Notes

* Use the `ubuntu` branch if you want to use it there. It uses different icons because the 1px transparent icon shifts the menu bar noticeably while it is barely visible on Elementary OS
* Because my desktop PC seemed to crash on poweroff, as seen in the `last` log, a variable is incremented every 60 seconds using `GLib.timeout_add_seconds(60, self.handler_timeout)` and written to the `total_today_time` file to track the uptime
* If you want to adjust the limit to show the alert icon, change `today_hour_limit` in `main.py`

## Screenshots

![](https://github.com/Gira-X/elementary-os-uptime-indicator/raw/master/screenshots/1.png)
![](https://github.com/Gira-X/elementary-os-uptime-indicator/raw/master/screenshots/2.png)

![](https://github.com/Gira-X/elementary-os-uptime-indicator/raw/master/screenshots/3.png)
![](https://github.com/Gira-X/elementary-os-uptime-indicator/raw/master/screenshots/4.png)
