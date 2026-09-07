# Device Lifecycle and Troubleshooting

## Overview

This section covers the core device lifecycle and troubleshooting tasks I completed within the Microsoft Intune Administration Lab. I reviewed the device decommissioning process for a managed Windows endpoint and performed practical troubleshooting and diagnostic tasks across the Intune environment.

These tasks demonstrate practical IT Support skills involving device lifecycle management, remote device actions, policy and compliance troubleshooting, application deployment troubleshooting, device management and check-in troubleshooting, and device synchronisation through Microsoft Intune.

---

# Task 1 - Reviewing the Device Decommissioning Process in Microsoft Intune

## Objective

Review the device decommissioning process for the managed Windows endpoint CLIENT01 using the remote Wipe action in Microsoft Intune, while preserving the device for the remaining troubleshooting tasks within the lab.

---

## Implementation

I reviewed the device decommissioning workflow for the managed Windows endpoint CLIENT01 within Microsoft Intune. From the device overview, I accessed the remote Wipe action and reviewed the available factory reset options and their potential impact on the endpoint.

The final wipe command was intentionally not executed, as CLIENT01 remained required for the troubleshooting and diagnostic tasks within the lab. This allowed the decommissioning procedure to be demonstrated and documented without removing the existing device configuration, applications, or management state.

---

## Navigation

```text
Microsoft Intune Admin Center
→ Devices
→ All devices
→ CLIENT01
→ Overview
→ Wipe
→ Review Wipe device options
→ Cancel without executing the wipe
```

---

## Outcome

The Microsoft Intune device wipe workflow was successfully reviewed for CLIENT01, demonstrating how an administrator can remotely initiate a factory reset when decommissioning a managed Windows endpoint. The destructive action was intentionally not executed, preserving CLIENT01 and its existing configuration for the remaining troubleshooting and validation tasks within the lab.

---

## Screenshot

**Figure 1:** The CLIENT01 device overview in Microsoft Intune showing the managed Windows endpoint and the available Wipe remote device action.

<img width="1919" height="914" alt="01 – Reviewing the Device Decommissioning Process in Microsoft Intune" src="https://github.com/user-attachments/assets/d1598bf7-315d-4a64-8ecf-5e2a65651ab8" />

**Figure 2:** The Wipe device confirmation screen showing the available factory reset options before execution. The final wipe command was intentionally not submitted to preserve CLIENT01 for further troubleshooting.

<img width="1919" height="914" alt="02 – Reviewing the Device Decommissioning Process in Microsoft Intune" src="https://github.com/user-attachments/assets/e0959b66-428d-4720-a93e-114e91a83ff8" />

# Task 2 - Troubleshooting an Intune Compliance Policy Error

## Objective

Investigate and resolve a Microsoft Intune compliance policy error affecting the managed CLIENT01 Windows device by identifying the individual policy setting responsible for the failure, applying an appropriate remediation, and verifying that the device successfully returns to a compliant state.

---

## Implementation

I investigated an Error affecting CLIENT01 under the Windows 10-11 - Compliance Policy in Microsoft Intune. Using the device compliance details, I reviewed the individual policy settings and isolated the issue to Encryption of data storage on device, which reported 2016281112 (Remediation failed), while the remaining applicable security controls were reporting as Compliant.

Because CLIENT01 is a VirtualBox-based lab endpoint and device encryption was not required for this scenario, I edited the compliance policy and changed Require encryption of data storage on device to Not configured. The policy was then reevaluated to confirm whether the configuration change resolved the compliance error.

---

## Navigation

```text
Microsoft Intune Admin Center
→ Devices
→ Compliance
→ Windows 10-11 - Compliance Policy
→ Device status
→ CLIENT01
→ Policy compliance: Error

CLIENT01
→ Device compliance
→ Windows 10-11 - Compliance Policy
→ Review individual compliance settings
→ Encryption of data storage on device: Error
→ 2016281112 (Remediation failed)

Microsoft Intune Admin Center
→ Devices
→ Compliance
→ Windows 10-11 - Compliance Policy
→ Properties
→ Compliance settings
→ System Security
→ Encryption
→ Require encryption of data storage on device: Not configured
→ Review + save

Microsoft Intune Admin Center
→ Devices
→ Compliance
→ Windows 10-11 - Compliance Policy
→ Device status
→ CLIENT01
→ Policy compliance: Compliant
```

---

## Outcome

The Windows 10-11 - Compliance Policy error was successfully resolved after isolating the failure to the device encryption requirement and adjusting the setting for the lab environment. Following policy re-evaluation, CLIENT01 changed from Error to Compliant, demonstrating the use of Intune's compliance reporting to identify a policy-level issue, apply targeted remediation, and verify successful resolution.

---

## Screenshot

**Figure 1:** Microsoft Intune showing CLIENT01 reporting an Error against the Windows 10-11 - Compliance Policy, establishing the initial compliance issue.

<img width="1919" height="913" alt="03 – Troubleshooting an Intune Compliance Policy Error" src="https://github.com/user-attachments/assets/9a9aef5a-7a49-4f40-b8dc-cb9fb25c0254" />

**Figure 2:** The CLIENT01 Device compliance view showing the Default Device Compliance Policy as Compliant while the custom Windows 10-11 - Compliance Policy reports an Error.

<img width="1918" height="916" alt="04 – Troubleshooting an Intune Compliance Policy Error" src="https://github.com/user-attachments/assets/076d22fe-954e-4150-867b-091a5960b986" />

**Figure 3:** Detailed compliance results showing the applicable security controls reporting as Compliant while Encryption of data storage on device reports Error — 2016281112 (Remediation failed), isolating the source of the compliance failure.

<img width="1919" height="913" alt="05 – Troubleshooting an Intune Compliance Policy Error" src="https://github.com/user-attachments/assets/bc5893c9-adba-4ce8-82cc-2b71a9558d10" />

**Figure 4:** The Windows 10/11 compliance policy configuration showing Require encryption of data storage on device changed to Not configured as the remediation for the lab environment.

<img width="1919" height="912" alt="06 – Troubleshooting an Intune Compliance Policy Error" src="https://github.com/user-attachments/assets/71c44479-fda5-4aa5-8ef0-5a0fc1236888" />

**Figure 5:** Microsoft Intune showing CLIENT01 reporting Compliant against the Windows 10-11 - Compliance Policy, confirming successful remediation.

<img width="1919" height="915" alt="07 – Troubleshooting an Intune Compliance Policy Error" src="https://github.com/user-attachments/assets/faa48210-a8a6-4234-853a-9d651b27e581" />

# Task 3 - Troubleshooting Intune Configuration Policy Deployment

## Objective

Troubleshoot an Intune configuration policy deployment issue affecting the managed CLIENT01 Windows device by investigating policy targeting, Microsoft Entra group membership, assignment status, and Intune reporting. Identify the root cause, apply the appropriate remediation, and verify that the configuration profile is successfully reassigned to the device.

---

## Implementation

I investigated the deployment of the Windows 10-11 - User Experience Configuration profile after CLIENT01 was no longer being targeted by the policy. The profile remained assigned to the Windows Devices security group, but investigation of the group in Microsoft Entra ID showed 0 members, confirming that CLIENT01 was no longer within the assigned group. I then reviewed the Intune Device assignment status report, which showed Total: 0, further confirming that no managed devices were currently within scope of the configuration profile.

To remediate the issue, I added CLIENT01 back to the Windows Devices security group and verified that it appeared as a direct member. After allowing the updated membership to propagate, I regenerated the Intune Device assignment status report. CLIENT01 then appeared with an Assignment status of Success, confirming that restoring the device's group membership successfully returned it to the configuration profile's assignment scope.

---

## Navigation

```text
Microsoft Entra Admin Center
→ Groups
→ All groups
→ Windows Devices
→ Members
→ Direct members
→ 0 group members found
→ Confirm CLIENT01 is missing from the assigned group

Microsoft Intune Admin Center
→ Devices
→ Configuration
→ Windows 10-11 - User Experience Configuration
→ Properties
→ Assignments
→ Included group: Windows Devices
→ Device assignment status
→ Generate report
→ Success: 0
→ Error: 0
→ Conflict: 0
→ Pending: 0
→ Total: 0

Microsoft Entra Admin Center
→ Groups
→ All groups
→ Windows Devices
→ Members
→ Add members
→ Select CLIENT01
→ Add
→ Refresh
→ Confirm CLIENT01 appears as a direct member

CLIENT01
→ Settings
→ Accounts
→ Access work or school
→ Workplace or school account
→ Info
→ Managed by JayTech
→ Sync

Microsoft Intune Admin Center
→ Devices
→ Configuration
→ Windows 10-11 - User Experience Configuration
→ Device assignment status
→ Generate again
→ CLIENT01
→ Assignment status: Success
→ Success: 1
→ Error: 0
→ Conflict: 0
→ Pending: 0
→ Total: 1
```

---

## Outcome

The configuration policy deployment issue was successfully traced to CLIENT01 being absent from the Windows Devices security group, placing the device outside the profile's assignment scope. After CLIENT01 was restored to the group and the updated membership propagated to Intune, the regenerated assignment report showed CLIENT01 – Success with Success: 1, Error: 0, Conflict: 0, Pending: 0, and Total: 1, confirming successful remediation and reassignment of the configuration profile.

---

## Screenshot

**Figure 1:** Microsoft Entra admin center showing the Windows Devices security group with 0 group members found, identifying that CLIENT01 was missing from the group used to target the Intune configuration profile.

<img width="1919" height="913" alt="08 – Troubleshooting Intune Configuration Policy Deployment" src="https://github.com/user-attachments/assets/c7688a5b-e18c-4951-9395-f32532c0ef19" />

**Figure 2:** Microsoft Intune showing the Windows 10-11 - User Experience Configuration assignment report with Total: 0, confirming that no managed devices were currently within the policy's assignment scope.

<img width="1919" height="912" alt="09 – Troubleshooting Intune Configuration Policy Deployment" src="https://github.com/user-attachments/assets/a6540b4c-7ee3-4fe7-a072-7bd9eca6b32a" />

**Figure 3:** Microsoft Entra admin center showing CLIENT01 restored as a direct member of the Windows Devices security group as the remediation for the configuration policy targeting issue.

<img width="1919" height="914" alt="10 – Troubleshooting Intune Configuration Policy Deployment" src="https://github.com/user-attachments/assets/014919e7-b2ef-4acf-b4cd-18e0b3047fb6" />

**Figure 4:** Microsoft Intune showing the regenerated Device assignment status report with CLIENT01 reporting Assignment status: Success and Success: 1, confirming successful remediation and policy reassignment.

<img width="1919" height="914" alt="11 – Troubleshooting Intune Configuration Policy Deployment" src="https://github.com/user-attachments/assets/ec2d59dc-88f8-4d39-8b50-a156b986b9e9" />

# Task 4 - Troubleshooting an Intune Win32 Application Deployment

## Objective

Troubleshoot a Microsoft Intune Win32 application deployment issue affecting 7-Zip 26.02 (x64 edition) on the managed CLIENT01 Windows device by investigating the reported installation failure, identifying the detection rule responsible, applying the appropriate remediation, and verifying that Intune successfully detects the application as installed.

---

## Implementation

I investigated the deployment of 7-Zip 26.02 (x64 edition) after Microsoft Intune reported CLIENT01 with a Failed device install status and the message The application was not detected after installation completed. I reviewed the application's detection rules and identified an incorrect MSI product code ending in 00001, preventing Intune from correctly detecting the installed application.

To remediate the issue, I corrected the MSI detection rule by changing the product code to the correct value ending in 00000 and saved the application configuration. I then initiated a manual Intune sync from CLIENT01 and refreshed the application deployment status. CLIENT01 subsequently reported Installed, confirming that the detection rule correction resolved the deployment issue.

---

## Navigation

```text
Microsoft Intune Admin Center
→ Apps
→ Windows
→ Windows apps
→ 7-Zip 26.02 (x64 edition)
→ Confirm application is assigned

7-Zip 26.02 (x64 edition)
→ Monitor
→ Device install status
→ CLIENT01
→ Status: Failed
→ Status details: The application was not detected after installation completed

7-Zip 26.02 (x64 edition)
→ Properties
→ Detection rules
→ Manually configure detection rules
→ MSI
→ Review MSI product code
→ Incorrect product code ending: 00001

Detection rules
→ Edit MSI detection rule
→ Correct MSI product code
→ Product code ending: 00000
→ OK
→ Review + save

CLIENT01
→ Settings
→ Accounts
→ Access work or school
→ Workplace or school account
→ Info
→ Managed by JayTech
→ Sync

Microsoft Intune Admin Center
→ Apps
→ Windows
→ Windows apps
→ 7-Zip 26.02 (x64 edition)
→ Monitor
→ Device install status
→ Refresh
→ CLIENT01
→ Status: Installed
```

---

## Outcome

The 7-Zip 26.02 (x64 edition) deployment issue was successfully traced to an incorrect MSI product code in the application's detection rule. After correcting the product code from the value ending in 00001 to 00000, syncing CLIENT01, and refreshing the deployment status, Microsoft Intune reported the application as Installed, confirming successful remediation.

---

## Screenshot

**Figure 1:** Microsoft Intune showing 7-Zip 26.02 (x64 edition) listed as an assigned Windows application, establishing the application being investigated.

<img width="1918" height="914" alt="12 – Troubleshooting an Intune Win32 Application Deployment" src="https://github.com/user-attachments/assets/a0cd5a31-653a-4d19-a157-d350a3bd91f0" />

**Figure 2:** The Device install status for 7-Zip 26.02 (x64 edition) showing CLIENT01 with a Failed status and the message The application was not detected after installation completed, establishing the deployment issue.

<img width="1919" height="914" alt="13 – Troubleshooting an Intune Win32 Application Deployment" src="https://github.com/user-attachments/assets/171f7d99-7a44-4d13-8774-c0c5042d9e18" />

**Figure 3:** The application's Detection rules showing the incorrect MSI product code ending in 00001, identifying the detection rule responsible for the failed application detection.

<img width="1919" height="914" alt="14 – Troubleshooting an Intune Win32 Application Deployment" src="https://github.com/user-attachments/assets/4795213a-940c-4c0e-8288-c1cfde93b870" />

**Figure 4:** The corrected Detection rules configuration showing the MSI product code ending in 00000, documenting the remediation applied to the Win32 application.

<img width="1919" height="914" alt="15 – Troubleshooting an Intune Win32 Application Deployment" src="https://github.com/user-attachments/assets/be4d5ff8-0923-4480-8f03-4ede98dc1bd5" />

**Figure 5:** The Device install status showing CLIENT01 with a status of Installed, confirming that the corrected detection rule resolved the application deployment issue.

<img width="1919" height="913" alt="16 – Troubleshooting an Intune Win32 Application Deployment" src="https://github.com/user-attachments/assets/7c03339e-b9a4-4614-9a51-5144d805b912" />

# Task 5 - Troubleshooting Device Management and Intune Check-In

## Objective

Investigate the device management and check-in status of CLIENT01, verify that the endpoint maintains its Microsoft Intune management connection, perform a manual device synchronisation, and confirm successful communication by validating an updated Last check-in time in the Microsoft Intune Admin Center.

---

## Implementation

I reviewed CLIENT01 within the Microsoft Intune Admin Center to investigate its device management and check-in status. The device was confirmed as Managed by Intune and Compliant, with the existing Last check-in recorded as 23/08/2026, 13:23. I then accessed Access work or school on CLIENT01 and reviewed the Managed by JayTech connection to confirm that the endpoint retained its organisational management connection and configured Management Server Address.

To verify and restore active communication with Intune, I initiated a manual Sync from CLIENT01, with the Device sync status confirming that the synchronisation completed successfully at 23/08/2026 16:33:57. I then returned to the Microsoft Intune Admin Center and refreshed the device record, where the Last check-in had updated from 13:23 to 16:34, confirming successful communication between CLIENT01 and Microsoft Intune.

---

## Navigation

```text
Microsoft Intune Admin Center
→ Devices
→ All devices
→ CLIENT01
→ Review Last check-in
→ Last check-in: 23/08/2026, 13:23

CLIENT01
→ Settings
→ Accounts
→ Access work or school
→ Workplace or school account
→ Info
→ Managed by JayTech
→ Review Management Server Address
→ Device sync status
→ Sync
→ Confirm: The sync was successful

Microsoft Intune Admin Center
→ Devices
→ All devices
→ Refresh
→ CLIENT01
→ Confirm updated Last check-in
→ Last check-in: 23/08/2026, 16:34
```

---

## Outcome

The device management connectivity of CLIENT01 was successfully investigated and verified. The endpoint retained its organisational management connection, the manual device synchronisation completed successfully, and the Last check-in in Microsoft Intune updated from 13:23 to 16:34. This confirmed successful communication between CLIENT01 and Microsoft Intune following the troubleshooting action.

---

## Screenshot

**Figure 1:** The CLIENT01 device record in Microsoft Intune showing the existing Last check-in of 23/08/2026, 13:23, establishing the device check-in status prior to troubleshooting.

<img width="1919" height="913" alt="17 – Troubleshooting Device Management and Intune Check-In" src="https://github.com/user-attachments/assets/ac129956-9c1d-4b50-9058-34b016f2be42" />

**Figure 2:** The Managed by JayTech management connection on CLIENT01 showing the configured Management Server Address and Device sync status, confirming that the manual synchronisation completed successfully at 23/08/2026 16:33:57.

<img width="1919" height="915" alt="18 – Troubleshooting Device Management and Intune Check-In" src="https://github.com/user-attachments/assets/67bb5dc9-8bbf-4968-a892-5a0435f2adfd" />

**Figure 3:** The CLIENT01 device record in Microsoft Intune showing the updated Last check-in of 23/08/2026, 16:34, confirming successful communication with Intune following the manual device synchronisation.

<img width="1919" height="913" alt="19 – Troubleshooting Device Management and Intune Check-In" src="https://github.com/user-attachments/assets/feb5bc61-f833-4e2d-ac4f-ced668aa7f82" />
