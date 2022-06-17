
# Working remotely

| Document Information |
------------------------|
| Category: Architecture Guidelines |
| Created: 2022-03-22 |
| Domain: Security |
| Author: pete.dingwall@education.gov.uk |
| References: PRI-SEC005 - Working Remotely |

## Guidelines to support users working remotely

The following guidelines are provided to guide Department users when working remotely and using public or home wireless connections to access services and resources provided by the Department.

**Exceptions** to the principles will be reviewed with the security and architecture governance teams and approved or declined as relevant, with all decisions tracked with rationale for future reference.

**Updates or modifications** to the principles can be requested via the owning architect, and will be reviewed against the roadmap and strategy and within the Architecture profession.

**Escalations** will be dealt with within the immediate leadership within the relevant architecture domain (up to DD level) and to the SLT by exception.

## Introduction

The Department's workforce are provided with laptop and tablet devices to enable flexible working to suit their personal and team's requirements. This flexibility was essential during the pandemic with regular requirements to work from home at short notice, and the need continues as our users adopt hybrid working patterns as part of our return to the office.

Our teams are diverse in nature and often geographically spread, requiring some to regularly travel to other offices for collaborative sessions or team working. The Department's remote access solution permits secure access whilst users are travelling to/from sites, and users will work flexibly whilst travelling to/from the site and whilst at the site.

These guidelines will help users to understand how to work securely and safely and protect access to the Department's systems and data.

## 1. Follow best practices to secure IT services at home

*Devices in your home can be vulnerable to malicious activity which could spread to other devices*

### Why?

Good cyber security begins at home. Security best practices should cover all of your devices at home, not just your work-issued computer and phone. Cyber criminals may seek to exploit your personal devices to steal your credentials or personal information about you, so they can impersonate you or access your personal systems for malicious use. This could lead to a compromise which could also affect your work devices and expose your credentials or the Department's data.

### How?

Follow standard guidance issued by the National Cyber Security Centre to help to understand risks and how to secure your services from cyber criminals. <https://www.ncsc.gov.uk/cyberessentials/advice>

## 2. Protect access to home WiFi services

*Follow best practices to ensure that access to your home wireless network is protected*

### Why?

Home WiFi solutions broadcast their signal beyond the boundary of your property and your service be snooped and re-used by others if not protected appropriately. This could lead to devices on your home network being accessed unintentionally and targeted for malicious activities.

### How?

- Follow the standard best practices provided by the supplier of your broadband service
- Use a strong password for your WiFi connection, do not use obvious or easily-guessable passwords
- Ensure that encryption is enabled for wireless on your broadband router (WPA2 is the most common and is normally enabled by default)

## 3. Be aware of surroundings when working remotely

*Working in public locations may inadvertently result in people gaining access to information*

### Why?

Working remotely in public places may inadvertently allow others to overhear private conversations or the Department's data, or even credentials to our services. *Shoulder-surfing* is a technique used by criminals to view private materials and credentials from users by sitting or standing close and watching their keystrokes or viewing their screens. This could be an opportunistic activity where someone overhears something of interest, or sees content when sitting next to someone on public transport, or where a cyber criminal identifies a user with a common working pattern and uses this to monitor activities and gain valuable information.

### How?

- Be conscious when working in public places and do not discuss confidential or sensitive matters if they may be overheard
- When entering passwords and PINs be aware of who is around you and whether your keystrokes could be viewed and re-used
- Do not work on sensitive or private content when working on public transport. If on a crowded train do not use your laptop or phone if it could easily be overlooked
- Do not identify yourself as a Department worker by wearing lanyard or security ID outside of the office, this may identify you as a target by criminals

## 4. Access services securely

*Ensure services used remotely support secure methods of access*

### Why?

Accessing services via unsecured or unencrypted connections exposes the data to potential snooping and monitoring, which could expose your credentials and lead to unauthorised access to Department services and data. Some services only require HTTP as the data being accessed does not require secured access, however most services default to using secure (aka HTTPS) access.

The risk of accessing less secure services when working from the Department's offices is mitigated as there are controls in place to stop non-Department users from accessing our standard networks, and monitoring in-place to identify malicious activity. However, when accessing these services via public networks the risk is increased with the potential for data to be visible by malicious users.

### How?

- Use the Department's provided remote access solution at all times when working remotely to ensure that access is encrypted and secured. This provides an additional layer of protection as all access is encrypted and protected, and all access is routed via the Department's web filtering services
- Ensure that any access to online service is using HTTPS (shown as a padlock to the left of the website in your web browser). This will ensure that data is encrypted and secured between your device and the web service
- Do not enter passwords on any sites or services which only use HTTP (shown as a website with a line crossed through in your web browser), as this data will be sent in plain-text and could be intercepted

## 5. Use Open Public WiFi services with caution

*Open Public WiFi can be used by criminals maliciously to gain access to your systems and data if not secured appropriately*

### Why?

Open Public wifi refers to WiFi services which are provided in public places such as on public transport or other open areas and do not require a password to connect, and are a convenient and cost-effective way of gaining access to Department's services if used appropriately.

Data transmitted across Open Public Wifi can be subject to monitoring and snooping if not secured appropriately, and can be used to monitor and gain access to credentials which could then allow criminals to access your device and the Department's systems and data.

Public Wifi names are well known and can be spoofed by criminals to capture data from your device or infect it with malware. If your device is set to connect automatically to WiFi services without passwords your device will send out 'beacons' looking for these WiFi networks and will connect autoamtically as soon as it finds one with the same name. Due to this it is very straightforward for a criminal to create a 'honeypot' WiFi hotspot with the same name which your device will connect to.

### How?

- Always connect to services securely, as outlined in Guideline 4
- Do not save the names of public WiFi services or allow your device to 'connect automatically'as this could lead to your device connecting to a malicious wifi network whch is impersonating a public wifi service.

## 6. Be conscious of the security provided by Secure Public WiFi and apply appropriate caution

*Secure Public WiFi which is secured with a password provides additional security, but should still be used with caution*

### Why?

Secure Public wifi refers to WiFi services which are provided by in public places such as cafes, bars and restaurants and require a password to connect. As with Open Public Wifi, these services are a convenient and cost-effective way of gaining access to Department's services and data whilst working remotely. Data transmitted across the Secure Public Wifi is encrypted using a standard protocol and is therefore not as susceptible to monitoring and snooping, but the security provided will be dependent on how well the Secure Public WiFi is configured.

Other users on the same WiFi network may be able to see your device and potentially monitor your traffic to gain access to credentials and your device. Whilst it is possible to configure the wireless network to isolate devices and mitigate this risk it is not enabled as default, so you should not assume that your device is secured once connected to the network.

Secure Public Wifi requires a password and is therefore less susceptible to common spoofing and impersonation with 'honeypot' wifi networks, however the names and passwords are generally displayed in open areas and therefore still vulnerable to a malicious user impersonating the network with the same password.

### How?

- Always connect to services securely, as outlined in Guideline 4
- Be cautious of Secure Public WiFi services and apply the same levels of caution as you would do with an Open Public Wifi service
- Be aware of the risks for saving the names of Secure Public WiFi or allowing your device to 'connect automatically'. It is still possible for this to lead to your device connecting to a malicious wifi network whch is impersonating a Secure Public Wifi service

## 7. Consider privacy when using Landing Pages

*Data shared in landing pages could be used inappropriately for mass marketing or to gather information for social engineering*

### Why?

A Landing Page is a web site which is used by WiFi providers to prompt users to accept terms and conditions, enter payment details or contact information before accessing their service. In most cases the provider simply needs acceptance of terms and conditions with a simple checkbox, but often this is accompanied with a request to enter contact details which the provider can then use to send 'targeted marketing material'.

You have no control over how this information will be shared and re-used, and could be sold to other marketing companies, or used maliciously to build profiles of individuals for targeted attacks in the future.

### How?

- Ensure that any 'landing pages' which require you to accept conditions or enter payment details are used within the 'captive portal' within the Department's Remote Access solution
- Do not provide payment information in a landing page unless you are sure that the sesion is protected and the portal shows the padlock in the address bar
- Do not provide detailed personal or work-related contact information when using landing pages to connect to Open Public Internet services. You do not know how this data will be used, and it could lead to targeted phishing emails or other social engineering
- Be cautious when sharing emails with Open Public Wifi services as the information may be used inappropriately and may lead to an increase in SPAM or phishing email
- Consider the use of a separate 'burner' email address or a masked email service such as Apple's "Hide my Email" to manage inappropriate mails

## 8. Apply caution when using personal devices

*Personal devices (aka BYOD) do not offer the same level of protection as Department-issued devices*

### Why?
A device issued by the Department will have security measures such as internet filtering and disk encryption enabled by default to secure data held on the device and to ensure that access to any online service is protected appropiately.

Users accessing the Department's services from a personal device will not have these same safeguards enabled by default as these are not pre-requisites for the BYOD service. Users with personal devices are able to access any internet site without filtering and download any applications they choose, which could leave them vulnerable to malicious activity.

### How?

- Ensure that all guidelines above are followed, with specific focus on principles 4-7 to ensure that access from personal devices is appropriately secured and resilient to malicious activity
 - Work online with content whenever possible from online services instead of copying data locally onto personal devices
  - Be aware of the classification of content used locally and ensure that it is protected appropriately
