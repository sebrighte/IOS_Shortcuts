# Tracker Public IP Address Updater

I run a Traccar server on Docker on my NAS that takes the position data from Tracker. This is done via DDNS using my public IP
The issue was my home public IP was chnaged (every few weeks) and my Tracker did not pick up the new IP adress so stopped updating its location
I had to check periodically to see if the tracker was working and manually update the ip address via SMS.

I sechule this to automaically run every day at a specified time.

This
* Takes the value of the DDNS URL
..* "Enter ddns url here"
* This is passed to the PublicIP shortcut that returns the IPV4 address
* This is compared against the stored value of the last Public IP address (to see if changed)
* If changed sends an SMS to the tracker to update the IP address of my Traccar Server


## Dependencies

#### [Download PublicIP Shortcut](https://github.com/sebrighte/IOS_Shortcuts/raw/main/PublicIP/PublicIP.shortcut)
#### [Download Memory Shortcut](https://github.com/sebrighte/IOS_Shortcuts/raw/main/PublicIP/PublicIP.shortcut)
