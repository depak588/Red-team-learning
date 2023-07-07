---
description: >-
  Reconnaissance is the process of collecting information about a person,
  organization, or system for the purpose of gaining knowledge or intelligence.
---

# Reconnaissance

### Active vs Passive Reconnaissance

**Passive** reconnaissance involves collecting information about a target system or network without directly interacting with it. This can include gathering information from public sources such as websites, social media profiles, and publicly available directories.

**Active** reconnaissance involves directly interacting with a target system or network in order to gather information. This can include techniques such as port scanning, network mapping, and vulnerability scanning.



### Let's start with Passive Reconnaissance

#### 1-) host command&#x20;

this command is used to find the IP address of a particular domain name or if you want to find out the domain name of a particular IP address

```bash
// host google.com    
google.com has address 142.250.192.174
google.com has IPv6 address 2404:6800:4002:82f::200e
google.com mail is handled by 10 smtp.google.com.
```

#### 2-)  nslookup command

is a command-line tool used to query the Domain Name System (DNS) to obtain information about a domain name or IP address.

```bash
// nslookup www.google.com    
Server:         192.168.80.2
Address:        192.168.80.2#53

Non-authoritative answer:
Name:   www.google.com
Address: 142.250.193.228
Name:   www.google.com
Address: 2404:6800:4002:825::2004
```

#### 3-) tracert command

The tracert or traceroute command is a network diagnostic tool used to trace the path that a packet takes from the computer running the command to a specified destination server or IP address.

```bash
// tracert google.com

Tracing route to google.com [2404:6800:4002:82f::200e]
over a maximum of 30 hops:

  1     2 ms     1 ms     2 ms  2409:40e3:100f:ae0::3
  2    46 ms    35 ms    47 ms  2405:200:520d:30:3924:0:3:5
  3    78 ms    51 ms    44 ms  2405:200:520d:30:3925::ff07
  4    51 ms    36 ms    44 ms  2405:200:801:2f00::284
  
```

#### 4-) dnsrecon command

DNSRecon is a Python script that provides the ability to perform: Check all NS Records for Zone Transfers.

```bash
// dnsrecon -d youtube.com
[*] std: Performing General Enumeration against: youtube.com...
[-] DNSSEC is not configured for youtube.com
[*]      SOA ns1.google.com 216.239.32.10
[*]      SOA ns1.google.com 2001:4860:4802:32::a
[*]      NS ns4.google.com 216.239.38.10
[*]      NS ns4.google.com 2001:4860:4802:38::a
[*]      NS ns3.google.com 216.239.36.10
[*]      NS ns3.google.com 2001:4860:4802:36::a
[*]      NS ns2.google.com 216.239.34.10
[*]      NS ns2.google.com 2001:4860:4802:34::a
[*]      NS ns1.google.com 216.239.32.10
[*]      NS ns1.google.com 2001:4860:4802:32::a
[*]      MX smtp.google.com 74.125.24.27
[*]      MX smtp.google.com 142.251.10.27
[*]      MX smtp.google.com 142.251.10.26
[*]      MX smtp.google.com 142.251.12.26
[*]      MX smtp.google.com 142.251.12.27
[*]      MX smtp.google.com 2404:6800:4003:c00::1a
[*]      MX smtp.google.com 2404:6800:4003:c11::1b
[*]      MX smtp.google.com 2404:6800:4003:c04::1b
[*]      MX smtp.google.com 2404:6800:4003:c04::1a
[*]      A youtube.com 142.250.193.78
[*]      AAAA youtube.com 2404:6800:4002:81b::200e
[*]      TXT youtube.com facebook-domain-verification=64jdes7le4h7e7lfpi22rijygx58j1
[*]      TXT youtube.com v=spf1 include:google.com mx -all
[*]      TXT youtube.com google-site-verification=QtQWEwHWM8tHiJ4s-jJWzEQrD_fF3luPnpzNDH-Nw-w
[*]      TXT _dmarc.youtube.com v=DMARC1; p=reject; rua=mailto:mailauth-reports@google.com
[*] Enumerating SRV Records
[+] 0 Records Found
```

#### 5-) wafw00f command

Identify and fingerprint Web Application Firewall products

```bash
// wafw00f poe.com   

                   ______
                  /      \                                                                                                                   
                 (  Woof! )                                                                                                                  
                  \  ____/                      )                                                                                            
                  ,,                           ) (_                                                                                          
             .-. -    _______                 ( |__|                                                                                         
            ()``; |==|_______)                .)|__|                                                                                         
            / ('        /|\                  (  |__|                                                                                         
        (  /  )        / | \                  . |__|                                                                                         
         \(_)_))      /  |  \                   |__|                                                                                         

                    ~ WAFW00F : v2.1.0 ~
    The Web Application Firewall Fingerprinting Toolkit                                                                                      
                                                                                                                                             
[*] Checking https://poe.com
[+] The site https://poe.com is behind Cloudflare (Cloudflare Inc.) WAF.
[~] Number of requests: 2

```

#### 6-) whois command

```
// whois google.com
   Domain Name: GOOGLE.COM
   Registry Domain ID: 2138514_DOMAIN_COM-VRSN
   Registrar WHOIS Server: whois.markmonitor.com
   Registrar URL: http://www.markmonitor.com
   Updated Date: 2019-09-09T15:39:04Z
   Creation Date: 1997-09-15T04:00:00Z
   Registry Expiry Date: 2028-09-14T04:00:00Z
   Registrar: MarkMonitor Inc.
   Registrar IANA ID: 292
   Registrar Abuse Contact Email: abusecomplaints@markmonitor.com
   Registrar Abuse Contact Phone: +1.2086851750
   Domain Status: clientDeleteProhibited https://icann.org/epp#clientDeleteProhibited
   Domain Status: clientTransferProhibited https://icann.org/epp#clientTransferProhibited
   Domain Status: clientUpdateProhibited https://icann.org/epp#clientUpdateProhibited
   Domain Status: serverDeleteProhibited https://icann.org/epp#serverDeleteProhibited
   Domain Status: serverTransferProhibited https://icann.org/epp#serverTransferProhibited
   Domain Status: serverUpdateProhibited https://icann.org/epp#serverUpdateProhibited
   Name Server: NS1.GOOGLE.COM
   Name Server: NS2.GOOGLE.COM
   Name Server: NS3.GOOGLE.COM
   Name Server: NS4.GOOGLE.COM
   DNSSEC: unsigned
   URL of the ICANN Whois Inaccuracy Complaint Form: https://www.icann.org/wicf/
>>> Last update of whois database: 2023-07-07T18:37:52Z <<<

```

#### 7-) netcraft website

netcraft is a website that provides various tools for analyzing and reporting on web server and website information.

{% embed url="https://sitereport.netcraft.com/" %}

#### 8-) DNS Dumpster

DNSdumpster is an online passive scanning tool to obtain information about domains, block addresses, emails, and all kind of information DNS related

{% embed url="https://dnsdumpster.com/" %}

#### 9-) whatweb command

The WhatWeb is a tool that is used to identify different web technologies including content management systems (CMS), blogging platforms, statistic/analytics packages, JavaScript libraries.

<pre class="language-bash"><code class="lang-bash"><strong>// whatweb zonetransfer.me
</strong><strong>
</strong>http://zonetransfer.me [301 Moved Permanently] Apache, Country[GERMANY][DE], HTTPServer[Apache], IP[5.196.105.14], RedirectLocation[https://zonetransfer.me/], Title[301 Moved Permanently], UncommonHeaders[do_not_hack_me], X-Powered-By[Sparkles]
https://zonetransfer.me/ [301 Moved Permanently] Apache, Country[GERMANY][DE], HTTPServer[Apache], IP[5.196.105.14], RedirectLocation[https://digi.ninja/projects/zonetransferme.php], Strict-Transport-Security[max-age=63072000], Title[301 Moved Permanently], UncommonHeaders[do_not_hack_me,permissions-policy], X-Powered-By[Rainbows and XSS&#x3C;script>alert(1)&#x3C;/script>]
https://digi.ninja/projects/zonetransferme.php [200 OK] Apache, Country[GERMANY][DE], Email[customer-service@zonetransfer.me,pippa@zonetransfer.me,robin@digi.ninj,robin@digininja.org], HTTPServer[Apache], IP[5.196.105.14], Meta-Author[Robin Wood - DigiNinja], Script[text/javascript], Strict-Transport-Security[max-age=63072000], Title[ZoneTransfer.me - DigiNinja], UncommonHeaders[do_not_hack_me,permissions-policy,upgrade,x-content-type-options,x-xss,referrer-policy,expect-ct,content-security-policy], X-Frame-Options[DENY], X-Powered-By[Rainbows and XSS&#x3C;script>alert(1)&#x3C;/script>]
</code></pre>

#### 10-) use wappalyzer browser add on

#### 11-) theHarvester

is used to gather open source intelligence (OSINT) on a company or domain.

```bash
// theHarvester -d website.com -b google,bing,yahoo,linkedin

```

#### 12-) Subdomain gathering&#x20;



Sublist3r&#x20;

{% embed url="https://github.com/aboul3la/Sublist3r.git" %}

knockpy

{% embed url="https://github.com/guelfoweb/knock.git" %}

assetfinder

{% embed url="https://github.com/tomnomnom/assetfinder.git" %}

amass

{% embed url="https://github.com/owasp-amass/amass.git" %}

### Now let's move over the acive intelligence gathering
