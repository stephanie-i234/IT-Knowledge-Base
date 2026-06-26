# Creating a New User on the Domain Controller</strong></p>

## Purpose 
This document provides the procedure for creating a user account in Active Directory

## Tools and Software Needed
- Windows Server 2022
- Active Directory Users and Computers (ADUC)

## Prerequsites
- Administrative credentials.
- Access to the Domain Controller.
- Active Directory Users and Computers installed.
- Determine the appropriate Organizational Unit (OU).

## Environment

* **Domain Controller:** Windows Server 2022
* **Client:** Windows 10 Pro
* **Domain:** corp.local

## Resolution Steps

1. Open Active Directory Users and Computers on the "Tools" Tab in the Server Manager

2. Navigate to the selected Organizational Unit.

3. Right-click the space in the folder and select "New" and under the drop down list choose "User"

4. A dialogue window with the creditials form should show up. Fill it out.

5. Select Next.

6. Configure the user's initial password.

7. Select the desired password options (for example, User must change password at next logon).

8. Select Next.

9. Select Finish.


#### Refer to HDD-003 for video demonstration

## Verification
Verify the user can successfully login to the domain from the client workstation.
