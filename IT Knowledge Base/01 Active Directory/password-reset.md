# Resetting a Password for a User</strong></p>


## Purpose
This document provides the procedure for resetting a password for a user account in Active Directory

## Tools and Software Needed
- Windows Server 2022
- Active Directory Users and Computers (ADUC)

## Prerequsites
- Administrative credentials.
- Access to the Domain Controller.
- Active Directory Users and Computers installed.
- User account exists in the domain.

## Symptoms
 User reports they cannot sign in after multiple password attempts, and they receive a message "The password is incorrect please try again"

## Environment

* **Domain Controller:** Windows Server 2022
* **Client:** Windows 10 Pro
* **Domain:** corp.local

## Cause 
User is unable to log into their account with their previous password

## Resolution Steps

1. Open Active Directory Users and Computers on the "Tools" Tab in the Server Manager

2. Locate the User in their Organizational Unit Folder, or use the "Action" Tab in the ADUC window click "Find" to search and locate the user account.

3. Right-click the account and select "Reset Password"

4. Check both "User must change password at next logon" and if account is locked also check "Unlock the user's account" 

5. Once filled out select ok

5. A dialoge box with a message "The password for [User Name] has been changed." will appear

6. Select Ok.

#### Refer to HDD-001 for video demonstration

## Verification
* Dialogue box with message "The password for [User Name] has been changed." 
* User is prompted to create a new password upon their next log in attempt.
* Verify the user can successfully login to the domain from the client workstation.
