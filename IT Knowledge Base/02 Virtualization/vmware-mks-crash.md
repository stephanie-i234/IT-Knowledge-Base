<p><strong style="font-size:24px;">VMware Workstation MKS Crash Troubleshooting</strong></p>


## Purpose

This document records the troubleshooting process used to investigate and recover from a VMware Workstation MKS (Mouse Keyboard Screen) unrecoverable error that interrupted virtual machine operation.

## Incident Summary

While restarting the client virtual machine during a help desk lab demonstration, VMware Workstation terminated unexpectedly and displayed an unrecoverable MKS error.

Error displayed:

```
VMware Workstation unrecoverable error: (mks)

Exception 0xc0000005 (access violation)
```

Following the crash, communication between the client workstation and the Domain Controller appeared to fail, preventing Active Directory administration and domain authentication.

## Environment

* VMware Workstation
* Windows Server 2022 Domain Controller
* Windows 10 Pro Client
* NAT Networking

## Symptoms

* VMware Workstation crashes.
* MKS unrecoverable error displayed.
* Domain Controller appears unavailable.
* Active Directory Users and Computers displays connection errors.
* DNS lookups fail.
* Domain login unavailable.

## Investigation Performed

The following troubleshooting steps were performed:

* Verified VMware network adapter configuration.
* Confirmed NAT networking remained enabled.
* Verified the virtual network adapter was connected.
* Inspected Device Manager for network adapter issues.
* Confirmed Active Directory services were running.
* Verified DNS configuration using `ipconfig`.
* Tested network connectivity using `ping`.
* Verified domain controller discovery using `nltest`.
* Performed DNS diagnostics.
* Reviewed VMware lock files.

## Root Cause

The exact root cause could not be conclusively identified.

Evidence suggests the VMware Workstation MKS process crashed unexpectedly, temporarily interrupting communication between the virtual machines. No evidence of Active Directory database corruption or permanent network configuration issues was found.

## Resolution

1. Close VMware Workstation.
2. Reopen VMware Workstation.
3. Start the Domain Controller.
4. Allow all Active Directory and DNS services to initialize.
5. Start the client workstation.
6. Verify network connectivity using `ping`.
7. Verify domain discovery using `nltest`.
8. Confirm Active Directory services are accessible.
9. Retry the original operation.

## Verification

* VMware launches successfully.
* Both virtual machines boot normally.
* Active Directory is accessible.
* DNS resolution succeeds.
* Domain authentication succeeds.
* Client workstation reconnects to the domain.

## Lessons Learned

* An MKS crash does not necessarily indicate Active Directory corruption.
* Always verify infrastructure services before assuming configuration loss.
* Allow Domain Controller services sufficient time to initialize after an unexpected shutdown.
* Use network and domain diagnostic commands before rebuilding or restoring virtual machines.
