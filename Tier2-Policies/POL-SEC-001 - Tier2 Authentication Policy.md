# Tier 2 Authentication Policy

| Category: Tier 2 Policy
------------------------|
| Expires: 2022-07-01
| Domain: Security
| References: ISPS020 - Authentication Policy
---

# Tier 2 Policy - Authentication

This is part of the hierarchy of policies from the main ISMS Policy Suite.

This Policy should be used alongside the Tier 1 Authentication Policy to provide the details and specific configuration items to successfully implement the Policy.

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
- Password must meet complexity requirements

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

**Self-Service Password Reset** will be **enforced** for all user accounts

## Multi-Factor Authentication

**MFA will be enforced for all accounts**, with **FIDO2 enabled** to enable multiple options for authentication factors

### Methods for MFA

MFA will be provided via the following methods:

1. Authenticator app on mobile phone (either prompt or One Time Passcode)
2. SMS one-time passcode on mobile phone
3. Physical FIDO2 Token

The preferred and recommended solution for users will be the Authenticator App, as this offers multiple methods of authentication, does not require further investment and is more secure than SMS.

Physical FIDO2 Tokens will be provided for users who do not have access to a mobile phone or cannot use a mobile phone app due to specific needs.

### MFA Reset

MFA will be configured to require to 2 methods to reset:

1. Mobile app notification
2. Mobile app code
3. Mobile phone
4. Office phone

## Enforcement of MFA

MFA prompts will be triggered automatically for additional authentication user when:

1. A user logs in after a period of no access
2. A user attempts to access a higher-privilege system
3. A user's login is identified as higher-risk due to a unknown location or logging in outside of normal working hours
4. A user's account is identified as risky or compromised
5. The DfE is in a heigtened risk situation

## Biometric Authentication

**Windows Hello for Business** will be **enabled** to allow all users to configure and implement.

Windows requires a PIN to be set when first enabling Biometric Authentication. The **Windows PIN length** will be set to **at least 6 alphaneumeric characters**

## Identity Protection
**AuzreAD Identity Protection** will be enabled and risk policies applied to trigger appropriate activities for risky logins

## Risk-based authentication policies

>> ***To-Do - Agree risk policies for triggers and events***

## SIEM integration

>> ***To-Do - Agree which events will be forwarded to SIEM and what will the SOC do with them***

## Joiner/Mover/Leaver Processes

>> ***To-Do - Agree policy settings for accounts to be disabled after inactivity***