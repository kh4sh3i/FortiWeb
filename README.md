# FortiWeb
FortiWeb is a web application firewall (WAF) that protects hosted web applications from attacks that target known and unknown exploits.

<img src="fortiweb.jpg" width="600px" />


## FortiWeb Models
* hardware
```
  • FortiWeb 100E
  • FortiWeb 400E
  • FortiWeb 600E
  • FortiWeb 1000E
  • FortiWeb 2000E
  • FortiWeb 3000E
  • FortiWeb 4000E
```
* virtual machine
```
  • Fortinet FortiWeb-VM01
  • Fortinet FortiWeb-VM02
  • Fortinet FortiWeb-VM04
  • Fortinet FortiWeb-VM08
```

## FortiWeb Licensing
* standard assets bunble
  * Security Service
  * Antivirus
  * IP Reputation
  * Geo DB
* advanced assets bundle
  * Credential Stuffing Defense
  * FortiSandbox Cloud


### Updating Signatures
* offline --> dont need lisense
* inline --> need lisence
Tip: iran is blocked by fortinet and we should use tunnel
```
config system autoupdate tunneling
  set status enable
  set address 192.168.1.10
  set port 8080
  set username fortiweb
  set password kh4sh3i
end
```


## FortiWeb Supported Platforms
```
• Apache Tomcat
• nginx
• Microsoft IIS
• JBoss
• IBM Lotus Domino
• Microsoft SharePoint
• Microsoft Outlook Web App (OWA)
• RPC and ActiveSync for Microsoft Exchange Server
• Joomla
• WordPress
```
by default fortiweb team design collection for above platform but we can create custom sign for other like Nuke,...



### Fortiweb operation mode
```
  Reverse Proxy
  True Transparent Proxy
  Transparent Inspection
  Offline Protection
  WCCP
```
Tip: best mode is reverse proxy and we can ssl offloading and check entire package!


### Administrative Domain (ADOM)
* Administrative domains (ADOMs) enable the admin administrator to constrain other FortiWeb administrators’ access privileges to a subset of policies and protected host names.
* ADOMs are not enabled by default.

### FortiWeb Sessions
* fortiweb use "cookiesession1" for controll application
* we can not change this cookie name until now!!

### Configuration Steps
* Configure Server Pool  ==> real server ip
* Configure Virtual Server  ===> up hand that connect to fortigate 
* Configure Server Policy ==> set a collection of rule for application
  * Configure X-Forwarded-For
  * Configure Signatures
  ```
    • Cross Site Scripting (XSS)
    • SQL injection and many other code injection styles
    • Remote File Inclusion (RFI)
    • Local File Inclusion (LFI)
    • OS commands
    • Trojans/viruses
    • Known Exploits
    • sensitive server information disclosure
    • credit card data leaks
  ```
  * Configure Web Protection Profile 





## best practice for config
```
  * Sensitive Data Logging
  * Enable Traffic Log (temp)
  * Enable Traffic Packet Log (temp)
  * Global Setting  (Syslog/SIEM)
  * WVS (Acunteix - Import in FWB VM - Analysis)
  * Machine Learning (First Alert, Then Alert & Deny)
  * IP Reputation
  * IP List
  * DoS Protection
  * Bot Mitigation !Biometric (100% Alert ---- Alert & Deny    Real Browser Enforcement)
  * URL Access
  * Allowed Method (Alert ----> Alert & Deny)
  * CORS Protection
  * HTTP Protocol (Alert ---- > Alert& Deny)
  * Parameter Validation (Client Side)
  * File Security - Web Shell Detection   (AV, Extension)
  * HTTP Header Security (XSS, X-Frame-Options)
  * SQL/XSS Syntax Based (Alert & Deny)
  * Signature (Tuning)
  * Authentication
  * URL Rewrintg
  * XFF
  * Global White List
  * Certificate
  * Protected Hostname
  * Load Balancing
  * LDAP Users Login to WAF
  * System Time
  * Backup and Restore (FTP, Local)
  * Change WAF Interface Port
  * Password Complexity
  * HA 
  * FortiGuard (Online Update , Tunneling)
  * Advanced Shared IP
  * Replacement Message
  * SNMP v3
  * DNS & Route
```
