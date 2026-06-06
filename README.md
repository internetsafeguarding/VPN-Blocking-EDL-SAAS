# VPN-Blocking-EDL-SAAS
A VPN Blocking Firewall EDL / SAAS service
# Using EDL’s to block VPN’s effectively firewalls.

In order to block commercial / free VPNs on a next generation firewall such as those made by PaloAlto Networks, fortinet and other advanced firewalls;  
External Data Lists (EDLs) or external sources are necessary.

The FW’s built in protocol / signature based blocking is effective against some protocols, IPSEC for example, but blocking that completely also breaks Wifi calling on mobile devices.  
Many ‘apps’ defined on the firewall detect some of a small number of commercial vpn providers traffic, but often not enough to stop the VPN from working for the user.

Blocking hosts or domains is helpful, but users can easily circumvent DNS controls to use external recursive DNS servers, via any number of encrypted protocols.   
Equally many VPNs use Content Delivery Networks (CDNs) and serverless cloud services and other application frameworks to bypass DNS filtering and controls.

Likewise URL filtering on the firewall is also effective in some cases with a properly curated and up to date EDL source, but many VPNs deliberately circumvent these URL controls, pretending to be other applications that are allowed, Many even bypassing solutions that fully decrypt TLS.

Blocking IP addresses on the firewall with EDLs is very effective at stopping these VPN’s. However you need to acquire a reliable, well curated EDL source for this, good enough to block the VPN completely and accurate enough not to cause false positives, up to date with the thousands of IP addresses that change daily.  
Many VPN’s are now very dynamic, so just updating the EDL daily is not good enough to be effective.

Likewise, just having very large lists of possible VPN IP Addresses , Domain / hostnames / ULS’s  is a high risk option, leading false positives, and the increased firewall load to deal with the lookups and EDL updates or overrunning the firewall capacity to process EDL entries..

[Internet-safeguarding](https://internet-safeguarding.com) offer a commercial EDL solution for blocking VPNs and provides some free EDL services.  
Registration is required even for free services

## Simple installation process:

On the firewall, create the EDL’s..  
![Image showing EDL create of IPv4 VPN list on PaloAlto Firewall](https://internet-safeguarding.com/wp-content/uploads/2026/06/CreateIPv4blockEDL-1.png) 
![Image showing EDL create of TOR IPv4 list on PaloAlto Firewall](https://internet-safeguarding.com/wp-content/uploads/2026/06/CreateTORblockEDL.png) 

Test the EDL works.  
![Image showing testing the EDL works](https://internet-safeguarding.com/wp-content/uploads/2026/06/CheckTOREDLworking.png)

Some Firewalls require you use the EDL in a policy and commit before the EDL is downloaded.

Same for URLs  
![Image showingURL / SNI EDL](https://internet-safeguarding.com/wp-content/uploads/2026/06/CreateURLblocklist-1.png)

Create the FW Policy or Rule using these EDLs.  
![Image showing Firewall Policy / rules on palo alto firewall](https://internet-safeguarding.com/wp-content/uploads/2026/06/CreateFWrulepolicywithedls.png)

Job done.
