---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configuring Ports to allow communication between the backup agent and {{site.data.keyword.backup_notm}} portal

The {{site.data.keyword.backup_full}} agent that is installed on your server needs to be able to communicate with the vault that you purchased. The Director host information for an {{site.data.keyword.backup_notm}} user account can be found in the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window} and the [{{site.data.keyword.cloud_notm}} console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://{DomainName}/){:new_window}.

Always register agents to the {{site.data.keyword.backup_notm}} portal and the directors by using the FQDN because the IP addresses for these services might change.

Your servers must communicate with the {{site.data.keyword.backup_notm}} portal and all AMP proxy servers for {{site.data.keyword.backup_notm}} portal to work correctly, regardless of the data center location.

```
https://evregister.service.softlayer.com TCP 8086,8087
```

Extra AMP proxy servers can be added as needed to handle more {{site.data.keyword.backup_notm}} agents that are registered to the {{site.data.keyword.backup_notm}} portal.

TCP Port 8086, 8087 must have access to 10.0.0.0/8.
{:important}

If you need to use more restrictive firewall rules, you might lose access to the {{site.data.keyword.backup_notm}} portal as the infrastructure is expanded. Currently, at minimum, your servers must allow access to the 10.0.82.0/24 and 10.2.118.0/24 subnets for TCP ports 8086, 8087. Other subnets might be used in the future as needed.

## Commercial

*{{site.data.keyword.backup_notm}} portal and AMP proxy servers*

- `https://ev-webcc01.service.softlayer.com` [10.0.82.12] 8086, 8087
- `https://evregister.service.softlayer.com` [10.0.82.12] 8086, 8087

*Commercial AMP proxy servers*

- evwebamp0901.service.softlayer.com [10.2.118.12] 8087
- evwebamp0902.service.softlayer.com [10.2.118.13] 8087
- evwebamp0903.service.softlayer.com [10.2.118.14] 8087
- evwebamp0904.service.softlayer.com [10.2.118.15] 8087
- evwebamp0905.service.softlayer.com [10.2.118.16] 8087
- evwebamp0906.service.softlayer.com [10.2.118.17] 8087
- evwebamp0907.service.softlayer.com [10.2.118.18] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

## Federal

*{{site.data.keyword.backup_notm}} portal and AMP proxy*

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087

The agent must allow the TCP port 2548 inbound on the private network. This setting allows Central Control and {{site.data.keyword.backup_notm}} portal to connect into the agent to manage it. Older versions of EVault used port 808.

The {{site.data.keyword.backup_notm}} management port (2548) can be changed by updating the registry key at: `HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber` (which is a `dword`) in Windows operating systems.

When it comes to connection settings, the difference between desktop Central Control and the Agent is often a point of confusion. The server-resident Agent connects to the {{site.data.keyword.backup_notm}} servers, while the desktop-utilized Central Control connects to your server, by using its address and the server's credentials to access it.
{:tip}
