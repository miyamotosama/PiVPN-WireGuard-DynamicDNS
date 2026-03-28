**In your router administrator environment**
* Try changing DNS values from ISP to Static DNS and choose Google's and/or CloudFlare's (8.8.8.8 | 1.1.1.1 )

**In the WireGuard GUI**
* In the config file for your user: try changing your DNS provider  (8.8.8.8 | 1.1.1.1 )
* Here, try also unticking the kill-switch.
  
**On your public domain controller**
* Are you using your Raspberry PI's public IP (your network's public IP)? This is the IP your DNS pointer should be pointing at.
*Try changing your router's DNS provider (8.8.8.8 | 1.1.1.1)

Do you see a pattern here? If you have successfully installed WireGuard, there is most likely a DNS problem.

