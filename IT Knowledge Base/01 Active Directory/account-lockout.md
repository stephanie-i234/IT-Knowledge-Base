# Unlocking a Locked Active Directory User Account 

## Purpose
This document provides the procedure for unlocking a user account in Active Directory after the account has been locked due to multiple failed sign-in attempts.

## Tools and Software Needed
- Windows Server 2022
- Active Directory Users and Computers (ADUC)

## Prerequsites
- Administrative credentials.
- Access to the Domain Controller.
- Active Directory Users and Computers installed.
- User account exists in the domain.

## Symptoms
User reports they cannot sign in after multiple password attempts.

## Environment

* **Domain Controller:** Windows Server 2022
* **Client:** Windows 10 Pro
* **Domain:** corp.local

## Possible Cause

The account has been locked after exceeding the configured number of unsuccessful logon attempts defined by the domain's account lockout policy.

## Resolution Steps

1. Open Active Directory Users and Computers on the "Tools" Tab in the Server Manager

2. Use the "Action" Tab in the ADUC window click "Find" to search and locate the user account.

3. Right-click the account and select Properties.

4. Open the Account tab in the Properties Window.

5. Use the checkbox to enable Unlock account.

6. Select Apply.

7. Select OK.

#### Refer to HDD-002 for video demonstration

## Verification
Verify the user can successfully authenticate to the domain from the client workstation.
