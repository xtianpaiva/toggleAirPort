# Overview

Bash script that will automatically turn your WiFi OFF if you connect your computer to an ethernet connection and turn it back ON when you unplug your ethernet cable/adapter/dongle.

Thanks to all folks in [https://gist.github.com/albertbori/1798d88a93175b9da00b](https://gist.github.com/albertbori/1798d88a93175b9da00b)

## Requirements

- Mac OSX 10+ (tested on Catalina)
- Administrator privileges

## Install

1. `cd toggleAirPort/`
2. `sudo cp ./toggleAirport.sh /Library/Scripts/`
3. `sudo chmod 755 /Library/Scripts/toggleAirport.sh`
4. `sudo cp ./com.mine.toggleairport.plist /Library/LaunchAgents/`
5. `sudo chown root /Library/LaunchAgents/com.mine.toggleairport.plist`
6. `sudo chmod 644 /Library/LaunchAgents/com.mine.toggleairport.plist`
7. `launchctl load /Library/LaunchAgents/com.mine.toggleairport.plist`

## Uninstall

1. `sudo rm /Library/Scripts/toggleAirport.sh`
2. `launchctl unload /Library/LaunchAgents`
3. `com.mine.toggleairport.plist`
4. `sudo rm  /Library/LaunchAgents/com.mine.toggleairport.plist`
5. `rm /var/tmp/prev_eth_on`
6. `rm /var/tmp/prev_air_on`
7. `rm /var/tmp/prev_toggle_airport_run`

## Misc

To debug, just run: `sudo /Library/Scripts/toggleAirport.sh` and add echo's wherever you'd like
[]([]())

If you get a message that Airport was already ON, try deleting `/var/tmp/prev_*`