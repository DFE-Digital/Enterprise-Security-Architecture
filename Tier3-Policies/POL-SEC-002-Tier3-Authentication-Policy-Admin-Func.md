# Tier 3 Authentication Policy

| Category: Tier 3 Policy |
| ------------------------ |
| Expires: 2022-07-01 |
| Domain: Security |
| References: ISPS020 - Authentication Policy |
| Document Status: **DRAFT** |
---

# Tier 3 Policy - Authentication

This is part of the hierarchy of policies from the main ISMS Policy Suite.

This Policy should be used alongside the Tier 2 Authentication Policy to provide the details and specific configuration items to successfully implement the Policy.

## Introduction and background

The DfE's authentication and authorisation approach is being updated to remain aligned to industry best practices and the NCSC's guidance. The following items delivered together will provide a defence-in-depth approach for authentication to our systems whilst providing greater flexibility and ease of use for our end-users.

**Passwords** for users will be deprecated in favour of *Passwordless Authentication*. Passwords remain the most common method for compromise of a user's account, either via a brute-force attack or social engineering compromise. By deprecating passwords for our users we will become more resilient to common attacks against our users.

Passwords will still be required as part of the overall authentication to the DfE's systems, but will not be the default method for authentication.

**Password Age** will be removed for users, enabling them to set a long-term complex password which will only be required when authenticating for the first time, or when setting up a new device.

**Self-Service**  will be provided for end-users to enable self-fix of common account problems, reducing impact on the service desk whilst improving end-user experience.

**Multi-Factor Authentication** will be implemented as part of the move to *Passwordless* and to provide support for policy-based and risk-based authentication to our services and data.

**Biometric Authentication** will become the default method for day-to-day authentication, removing the need to enter passwords when accessing via the end-users standard devices.

The DfE's standard Windows devices all include biometric authentication via either Windows Hello cameras or compatible fingerprint readers.

**Identity Protection** will be enabled to provide visibility of improper or anomalous authentication activities. Identity Protection will highlight common inappropriate use such as account sharing/re-use, and identify common anomalous activity such as logins from unknown locations or outside of a user's normal working patterns.

**Risk-based access policies** will be enabled to apply additional authentication factors or invoke password resets in the event of anomalous or risky authentication activity. Importantly, a user's access will not be revoked in the event of a risk-based policy being triggered, instead the user will be required to provide additional authentication methods to validate their login attempt or address any potential account compromise

**SIEM Integration** will provide visibility of high-risk authentication attempts, which might be signs of an individual user account compromise or a wider and complex attack which would require additional action.

**Joiner/Mover/Leaver processes** will be strengthened to capture any inactive accounts and regularly review access to systems to ensure that access provided is still relevant.

# Policy settings and specific configuration

## Password Policies

### Standard accounts

- Minimum password length is 14 characters
- Password history is set to 24 passwords
- Minimum password age is 1 day
- Maximum password age **will be removed**
- Enforce password lockout after 6 bad passwords
- Reset failed login attempts after 60 minutes
- Account will lockout for 60 minutes

### Admin accounts

- Minimum password length is 14 characters
- Password history is set to 24 passwords
- Minimum password age is 1 day
- Maximum password age is 60 days
- Enforce password lockout after 6 bad passwords
- Reset failed login attempts after 60 minutes
- Account will lockout for 60 minutes
- No complexity requirements to support the use of passphrases

### Service/functional accounts

- Minimum password length is 14 characters
- No Password History
- No Password Age
- Enforce password lockout after 6 bad passwords
- Failed login attempts will not be reset
- Account will not automatically clear lockout
- Password must meet complexity requirements
- Account must have a named owner

## Self-Service

**Self-Service Password Reset** will be **available** for all user accounts

**Self-Service Account Unlock** will be **available** for all user accounts. This will allow users to unlock their accounts via self-service instead of waiting for the 60 minute automatic unlock specified in the policy.

## Multi-Factor Authentication

**MFA will be available for all accounts**, with **FIDO2 enabled** to enable multiple options for authentication factors

### Methods for MFA

MFA will be provided via the following methods:

1. Authenticator app on mobile phone (either prompt or One Time Passcode)
2. SMS one-time passcode on mobile phone (deprecated)
3. Physical FIDO2 Token

The preferred and recommended solution for users will be the Authenticator App, as this offers multiple methods of authentication, does not require further investment and is more secure than SMS.

*The SMS Auth Factor is identified as **deprecated** to prepare for the anticipated removal as a factor in the future, due to the potential of spoofing*

Physical FIDO2 Tokens will be provided for users who do not have access to a mobile phone or cannot use a mobile phone app due to specific needs.

### MFA Reset

MFA will be configured to require to 2 methods to reset:

1. Mobile app notification
2. Mobile app code
3. Mobile phone
4. Office phone

## Use of MFA

MFA will be applied for all users who have enrolled with passwordless authentication. MFA prompts will be triggered automatically for additional authentication when:

1. A user logs in after a period of no access
2. A user attempts to access a higher-privilege system
3. A user's login is identified as higher-risk due to a unknown location or logging in outside of normal working hours
4. A user's account is identified as risky or compromised
5. The DfE is in a heightened risk situation

*MFA will not be applied for users who have not enrolled with passwordless authentication, but will be enforced for users who access higher-privileged systems (item 2 above).*

*Users who have not enrolled with passwordless authentication will need to reset their password if their account is identified as risky or compromised. (Item 4 above).*

## Biometric Authentication

**Windows Hello for Business** will be **enabled** to allow all users to configure and implement.

Windows requires a PIN to be set when first enabling Biometric Authentication. The **Windows PIN length** will be set to **at least 6 alphaneumeric characters**

## Identity Protection
**AuzreAD Identity Protection** will be enabled and risk policies applied to trigger appropriate activities for risky logins

## Password Protection
**AzureAD Password Protection** will be enabled for all accounts to ensure that users cannot select easily guessed and vulnerable passwords.

## Joiner/Mover/Leaver Processes

1. Checks are carried out at present by the Department's operational teams for inactive accounts and will be unaffected by this policy
2. Inactive accounts will be disabled but not removed at present due to ongoing enquiries across the Department. This will be updated once the enquiry has concluded

---
## Future planned updates to the policy

### Risk-based authentication

1. Define risk policies, triggers and events

2. Categorise account types and appropriate risk policies to apply

### SIEM integration

1. Define which authentication events will be forwarded to SIEM

2. Define suitable actions for the SOC and operational teams

### Joiner/Mover/Leaver

1. Define activities which are carried out for inactive accounts
2. Track how enquiries which will impact the retention of accounts are captured and updated