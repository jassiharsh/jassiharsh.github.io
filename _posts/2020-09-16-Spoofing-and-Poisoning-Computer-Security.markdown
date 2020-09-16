---
layout: post
title:  "Spoofing and Poisoning"
date:   2020-09-16 21:03:36 +0530
categories: Computer Security
---

I will explain spoofing and poisoning from computer security in this post. 

Spoofing by definition means to hoax or trick someone.  Spoofing attacks using technology has been around for decades. One of the earliest methods of electronic spoofing began in the early 1990s. This method involved telephones and changing caller IDs to scam people. Caller ID spoofing is still a problem today but this technique has made its way on to the Internet and has become one of the most common attack methods used today. Spoofing on the Internet is used to either redirect traffic to another location or hide the source of packets.  The three common methods of spoofing are IP spoofing, MAC spoofing, and ARP spoofing. 

IP spoofing involves changing the IP information within a packet. A primary use of IP spoofing is to hide the source of the network packet. Using fake originating IP addresses an attacker can use this method in a DDoS attack or redirect responses to a victim. 

MAC spoofing is another attack method where instead of changing the logical address the attacker falsifies the physical MAC address in the Ethernet frame. This type of attack is more complicated than IP spoofing but at the same time is it more dangerous. By MAC spoofing an attacker can gain access to networks that utilize access control lists for permitted devices or port-based security. 

Lastly, ARP spoofing is sort of a combination of IP and MAC spoofing but the attacker does not modify the packets or Ethernet frames. Instead, the attack occurs at the routing level attacking the ARP table. An ARP table is a lookup table that keeps an association between IP addresses and MAC addresses. An ARP spoof tampers with this table and changes these associations with malicious IP or MAC addresses. 

Preventing spoofing attacks is a constant battle but there are things you can do to help mitigate the risk of becoming a victim of one. Implementing packet filtering is a defensive measure where you block Internet traffic from malicious sources.  Access Control Lists can also be used to deny access and filter network traffic.

MAC address spoofing however requires a little different approach. In our organization, we have found that preventing MAC address spoofing is a bit more involved and requires a proactive monitoring approach along with port-based security. We have also found situations where people have shared a USB to Ethernet cable between computers causing a false positive. This is because the MAC address of the cable showed up on more than on IP address.   Implementing port-based security on the physical LAN and certificate-based authentication on WiFi has helped. However, we are still required to actively monitor the network traffic and rely on alerts from our Intrusion Detection System. 