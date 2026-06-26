<p><strong style="font-size:24px;">DNS Server Configuration and Troubleshooting</strong></p>


## Purpose

This document provides the procedure for verifying and correcting DNS server settings on a Windows client to restore communication with the Active Directory domain.

## Tools and Software Needed

* Windows Server 2022
* Windows 10 Pro Client
* Command Prompt (Administrator)
* Control Panel

## Prerequisites

* Administrative credentials
* Access to the client workstation
* Domain Controller is powered on and operational
* Correct DNS server IP address is known

## Symptoms

* Unable to contact the domain controller
* Domain login fails
* Active Directory services cannot be located
* `nslookup` fails to resolve the domain
* Domain resources are unavailable

## Environment

* **Domain Controller:** Windows Server 2022
* **Client:** Windows 10 Pro
* **Domain:** corp.local

## Possible Cause

The client workstation is configured with an incorrect DNS server address, preventing it from locating the domain controller.

## Resolution

1. Open **Command Prompt** as an Administrator.
![Command Prompt opened as Administrator](dns-step-1.png)

2. Run `ipconfig /all` to verify the current network configuration and DNS server address.
![Cmd Prompt ipconfig](dns-step-2.png)

3. Run `nslookup` to verify DNS name resolution.
![Successful nslookup output verifying DNS resolution](dns-step-3.png)

4. Open **Control Panel** and navigate to **Network and Internet > Network and Sharing Center**.
![Windows Search Control Panel](dns-step-4.png)

5. Select the active **Ethernet** connection.
![Network and Sharing Center window](dns-step-5.png)


6. Double-click **Internet Protocol Version 4 (TCP/IPv4)**.
![Ethernet Properties window](dns-step-7.png)

7. Select **Use the following DNS server addresses**.

8. Enter the IP address of the Domain Controller's DNS server.
![TCP/IPv4 Properties window](dns-step-9.png)

9. Select **OK** to save the changes.
10. Open Command Prompt and run `ipconfig /flushdns`.
11. Run `nslookup` again to verify successful DNS resolution.
![Successful nslookup verification](dns-step-11&12.png)


#### Refer to HDD-05 for video demonstrations

## Verification

* `nslookup` successfully resolves the domain.
* The client can locate the Domain Controller.
* Domain authentication succeeds.
* Network communication with the domain is restored.

## Lessons Learned

* Use `ipconfig /all` to verify the configured DNS server.
* Use `nslookup` to test DNS resolution.
* Active Directory depends on DNS for locating domain services.
* An incorrect DNS server configuration can prevent users from logging into the domain.