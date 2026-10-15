# iOS Hardening and Privacy Guide

## Introduction

This guide provides practical settings and best practices to strengthen security and privacy on iOS devices. 

This guide provides practical settings and best practices to strengthen security and privacy on iOS devices. It focuses on limiting data exposure and account compromise if a device is stolen or lost, while supporting reliable recovery from backups, on the other side, it also tries to keep the device usable on a daily basis, paranoid security guide may be developed later.

The target version is iOS 26.5.1; settings and feature availability should be checked when applying the guide to other versions, but most of the content should be compatible with any software version.


## Main topics

1. Threat model
2. Software updates policy
3. Lock screen access and device theft protection
	1. Control centre
	2. Notification centre
	3. Carrier service
	4. Apple pay
4. Device passcode, Face ID, and Touch ID
5. Apple Account security and account recovery
6. 
7. Application permissions and privacy settings
8. Network connectivity and secure browsing
9. Backups and data protection
10. Advanced protections and Lockdown Mode
11. Security checklist and verification


## 1. Threat model

In order to improve the defense, the approach is to identify, describe and plan the most probable scenarios. 


### 1.1 Main scenarios
This guide focuses on two scenarios: 
- **Device theft**.
- **Device loss**.  
In both cases, the owner loses physical control of the iPhone. The priorities are to protect personal information, prevent unauthorized account access, and restore access to essential services and backed-up data.

Theft involves someone deliberately taking the device. Loss may initially involve no attacker, but an opportunistic finder could keep it or attempt to access its contents. Preparation should therefore address both scenarios.

### 1.2 Assets to protect

- **Personal data:** photos, messages, contacts, documents, and location information.
- **Accounts and identity:** the Apple Account, email, saved credentials, and active application sessions.
- **Financial access:** banking applications, payment services, and information that could support fraud.
- **Recovery methods:** the phone number, authenticator codes, recovery information, and trusted devices.
- **Data availability:** backups and the ability to recover without the missing iPhone.

### 1.3 Threat scenarios

| Type              | Scenario                                                     | Main concern                                                                                                       |
| ----------------- | ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| Device theft      | A locked iPhone is stolen.                                   | An unauthorized person attempts to unlock it or obtain information exposed on the lock screen.                     |
| Device theft      | The iPhone is taken while unlocked.                          | The person may have an opportunity to use open applications and existing sessions.                                 |
| Device intrussion | The thief knows or has observed the passcode.                | The passcode can no longer be treated as a reliable barrier; account access and recovery are also at risk.         |
| Device loss       | The device remains unavailable                               | The owner loses access to local data, communications, or authentication methods needed to recover accounts.        |
| Device loss       | Someone contacts the owner claiming to have found the device | A fraudulent recovery message may try to obtain credentials, verification codes, or changes to device protections. |

### 1.4 Assumptions and boundaries

Assume the unauthorized person has physical possession of the iPhone and may keep it offline. The device may be locked or unlocked, and the passcode may be unknown or compromised. Access to another trusted device, the primary phone number, and recent backups must be assessed separately rather than assumed.

The baseline model covers opportunistic theft and misuse by a finder. Targeted spyware, specialist forensic attacks, and coercion are outside its scope; they require a separate assessment. Hardening reduces risk but cannot guarantee device recovery or prevent every disclosure.

Theft or loss is always disruptive and WILL occur at the worst possible time. The goal is to balance security and reliable backups to minimize the impact.

### 1.5 Security priorities

1. Minimize information and actions available without authentication.
2. Reduce the impact of an exposed passcode or an unlocked device.
3. Protect account and recovery access independently of the iPhone.
4. Prepare a response that can be initiated from another device.
5. Recover backups and verify the recovery process before an incident.
6. Re-gain access to your authentication methods.

Successful preparation means a missing iPhone does not automatically lead to account compromise or permanent loss of essential data. Each setting in the following chapters should be evaluated against these priorities and its effect on everyday usability.

## 2. Software updates policy

Keeping iOS and installed applications up to date is essential to protect the device against known vulnerabilities and maintain reliable operation. Apple identifies software updates as one of the most important measures for device security. [Apple security releases](https://support.apple.com/en-us/100100)

Updates should nevertheless be installed with awareness of their urgency and potential impact. For major upgrades or routine releases without urgent security fixes, consider waiting a few days and checking for widespread reports of battery, connectivity, or application problems affecting your iPhone model. Install promptly once the release appears stable, and ensure a recent backup is available beforehand. **Do not apply this waiting period to urgent security fixes, particularly those addressing vulnerabilities already being exploited.**

ChatGPT can help summarize recent reports and release notes. Ask for current information about the exact iOS version and iPhone model, with links to sources. Verify those sources before deciding: a summary or the absence of reported problems does not guarantee that an update will be trouble-free.

Go to Settings > General > Software Update
It should be set at least as "Download only", to be ready at anytime.

The suggested setup for iOS software updates should looks like this:

![[2.0.0-sw-update-comb.jpg]]

## 3. Lock screen access and device theft protection

In this section you'll setup protection in the case of theft or loss for locked iOS device.

### 3.1 Lock screen protection

Even locked there is a lot of things that can be done from lock screen if there is no active protection, for example:

- Control centre: allows management of critical actions, such as network access, apple pay and (less critical) music status.
- Notification Centre: contains the notifications that may include personal conversations or more sensitive content such as SMS authentication/verification codes.
- Carrier Service: allows disabling/enabling the carrier connectivity.

Go to Settings > Face ID & Passcode (enter your passcode)

Navigate down until "Allow Access When Locked", you'll see the following:

![[3.1.lock.jpg]]

Disable:
- Notification Centre (prevent access to chats, SMS, etc).
![[3.1notification.jpg]]
- Control Centre (main functions)
- Lock Screen Widgets (prevent home automation usage)
- Siri
- Home Control
- Wallet (cards and identifications)
- Workout Health Data (any health data is private)

You may leave enabled:
- Today View and Search
- Return missed calls (you might be able to be responded if someone finds it and you call).

### 3.2 Apple pay

Apple Pay is always requiring FaceID for usage, but as seen above, it should also remain disabled, because in other way the thief could be able to see available cards, or even name or flight information.
![[3.1.applepay.jpg]]
Above. What can be seen without authentication.


## 4. Carrier Service

This setting maybe obvious for more modern lines, but older ones might have a physical SIM card, a thief by pulling it out might disable the phone's ability to communicate.

In this case, a workaround is to have a virtual SIM that cannot be extracted, and in conjuntion with Control Centre protection, the thief cannot switch of carrier service.
Note: take into account that this is a mitigation, underground or in tunnel the carrier service will also be innaccesible, but at least the last location will be saved.


## Documentation conventions

- Write all documentation in English and Markdown.
- Record the iOS version used to verify each procedure.
- Include the settings path, expected result, and relevant usability tradeoffs.
- Reference official Apple documentation for technical claims.
- Remove personal information from screenshots before committing them.

## Screenshots

Store screenshots in [`screenshots/`](screenshots/). See the [screenshot conventions](screenshots/README.md) for naming and Markdown usage.