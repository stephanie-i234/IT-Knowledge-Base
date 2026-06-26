<p><strong style="font-size:24px;">Disk Thrashing Troubleshooting</strong></p>


## Purpose

This document provides the troubleshooting procedure for diagnosing and reducing excessive disk utilization on a Windows workstation to improve overall system performance and application responsiveness.

## Tools and Software Needed

* Windows 10/11 OS
* Task Manager
* Resource Monitor (resmon)
* Windows Security
* Services Console (services.msc)

## Prerequisites

* Administrative credentials
* Access to the affected workstation
* User has saved any open work before stopping services or making system changes

## Symptoms

* Slow application launches
* Delayed response when opening files or programs
* High Disk utilization (90–100%) in Task Manager
* Increased hard drive activity
* Increased cooling fan speed due to sustained system activity
* Applications becoming unresponsive or requiring a restart

## Environment

* **Operating System:** Windows 10/11

## Possible Cause

* Excessive background services
* Windows Defender real-time scanning
* OneDrive synchronization
* Windows indexing
* SysMain (Superfetch)
* Multiple applications competing for disk resources

## Resolution

1. Open Task Manager via the windows search bar and select the Processes tab.
![Task Manager windows search](hdu-step-1.png)
![Task Manager, Drive Focused window](hdu-step-1.5.png)
2. Sort processes by Disk usage to identify the highest disk consumers.
![Run dialogue, resmon](hdu-step-2.png)
3. Press Windows + R, type resmon, and open Resource Monitor to obtain additional disk activity information.
![Resource Monitor window](hdu-step-3.png)
4. Pause OneDrive synchronization if it is actively consuming disk resources.
![OneDrive Synchronization](hdu-step-4.png)
5. If additional troubleshooting is required, press Windows + R, type services.msc, and open the Services console.
![Run dialogue box, service.msc](hdu-step-5.png)
![Services window](hdu-step-5.5.png)
6. Review services that may contribute to excessive disk usage (for example, SysMain). Stop or temporarily disable services only when appropriate and after understanding their purpose.
	Examples of services or processes that may contribute to high disk utilization include:

	- SysMain (Superfetch)
	- Windows Search (Indexing)
	- OneDrive synchronization
	- Windows Defender real-time scanning
	- Windows Update
	- Delivery Optimization

![Services window, pausing service](hdu-step-6.png)
7. Open Windows Security.
![Window Security windows search](hdu-step-7.png)
8. Navigate to Virus & threat protection.
![Window Security settings window](hdu-step-8.png)
9. Select Manage settings under Virus & threat protection settings.
![Windows Security, Virus & threat window](hdu-step-9.png)
10. If appropriate for a controlled troubleshooting or lab environment, temporarily disable Real-time protection.
![Virus & threat setting window](hdu-step-10.png)
11. Continue monitoring disk utilization using Task Manager and Resource Monitor to verify whether utilization decreases.



## Verification

* Disk utilization remains at normal operating levels during regular use.
* Applications respond normally.
* Overall system responsiveness improves.
* Cooling fan activity decreases after disk utilization returns to normal.

## Optional Optimization

If the workstation is not used for gaming or Xbox-related services, the following services may be disabled to reduce unnecessary background activity:

* Xbox Accessory Management Service
* Xbox Live Auth Manager
* Xbox Live Game Save
* Xbox Live Networking Service

Only disable these services if they are not required by the user or organization.

## Lessons Learned
* Use Task Manager and Resource Monitor together when diagnosing disk performance issues.
* Identify high disk utilization before attempting corrective actions.
* Background services can significantly affect system performance.
* Always determine the root cause before disabling Windows services.
* Windows Defender real-time protection should only be temporarily disabled in a safe testing or lab environment and should be re-enabled after troubleshooting.