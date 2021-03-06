# Python3 script to display a PC's today uptime

For Elementary OS and Ubuntu.

Displays today's uptime with Gtk's AppIndicator3 library and displays a warning icon once a certain amount of hours (by default 5) are exceeded.

The warning icon is the `clock-alert` icon with more padding from https://materialdesignicons.com/

## Notes

* If you get a `ValueError: Namespace AppIndicator3 not available` crash, you have to run `sudo apt install gir1.2-appindicator3-0.1`
* The script checks if Elementary OS or Ubuntu is running automatically to adjust the menu icon
  * It uses different icons because the 1px transparent icon (used for Elementary OS) enlargens the menu item on Ubuntu. Every icon has the same fixed size there and I was not able to completely remove the icon unfortunately, so a dummy image had to be used
* Because my desktop PC frequently crashed on poweroff, as reported by `last`, a variable is incremented every 60 seconds using `GLib.timeout_add_seconds(60, self.handler_timeout)` and written to the `total_today_time` file to track the uptime
* If you want to adjust the limit to show the alert icon, change `today_hour_limit` in `main.py`

## Screenshots

![](https://github.com/Gira-X/elementary-os-uptime-indicator/raw/master/screenshots/1.png)
![](https://github.com/Gira-X/elementary-os-uptime-indicator/raw/master/screenshots/2.png)

![](https://github.com/Gira-X/elementary-os-uptime-indicator/raw/master/screenshots/3.png)
![](https://github.com/Gira-X/elementary-os-uptime-indicator/raw/master/screenshots/4.png)
