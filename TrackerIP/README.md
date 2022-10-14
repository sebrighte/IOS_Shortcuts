# Tracker Public IP Address Updater

I run a Traccar server on Docker on my NAS that takes the position data from Tracker. This is done via DDNS using my public IP
The issue was my home public IP was chnaged (every few weeks) and my Tracker did not pick up the new IP adress so stopped updating its location
I had to check periodically to see if the tracker was working and manually update the ip address via SMS.

I sechule this to automaically run every day at a specified time.

I could just send a text every day but this method reduces costs as it only sends update when IP address has changed.
I could also simplify by getting my external IP address when on my WiFi, this method works wherever I am, even on cellular networking

This
* Takes the value of the DDNS URL
  * "Enter ddns url here"
* This is passed to the PublicIP shortcut that returns the IPV4 address
  * Returned as text
* This is compared against the stored value of the last Public IP address (to see if changed)
  * Pass disctionary to memory to get last IP stored
* If changed sends an SMS to the tracker to update the IP address of my Traccar Server
  * Show notification that IP has been updated
  * Send adminIP udate to tracker


## Dependencies

#### [Download PublicIP Shortcut](https://github.com/sebrighte/IOS_Shortcuts/raw/main/PublicIP/PublicIP.shortcut)
#### [Download Memory Shortcut](https://github.com/sebrighte/IOS_Shortcuts/raw/main/PublicIP/PublicIP.shortcut)
#### [Traccar Docker Image](https://github.com/traccar/traccar-docker) (Requies a SQL databse as well, I used PostGres)
