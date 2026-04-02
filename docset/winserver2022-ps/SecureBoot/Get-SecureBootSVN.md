---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.SecureBoot.Commands.dll-Help.xml
Module Name: SecureBoot
ms.date: 04/01/2026
online version: https://learn.microsoft.com/powershell/module/secureboot/get-securebootsvn?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
title: Get-SecureBootSVN
---

# Get-SecureBootSVN

## SYNOPSIS
Gets Secure Boot Security Version Number (SVN) information and compliance status for the system firmware and boot manager.

## SYNTAX

### YAML
```
Get-SecureBootSVN
[-BootManagerPath <String>] 
[<CommonParameters>] 
```


## DESCRIPTION
The **Get-SecureBootSVN** cmdlet retrieves Secure Boot Security Version Number (SVN) information from the system’s UEFI firmware and the currently installed or specified boot manager.  
It evaluates whether the system is compliant with the firmware’s Secure Boot policy. The cmdlet must be run from an elevated PowerShell session on a UEFI-based system with Secure Boot enabled.

## EXAMPLES

### Example 1: Get current Secure Boot SVN compliance status

### YAML
```
Get-SecureBootSVN
```

This command retrieves the firmware’s required SVN, the current boot manager’s SVN, any staged (pending) SVN updates, and evaluates whether the system is compliant.

### Example 2: Check SVN compliance for a specific boot manager file

### YAML
```
Get-SecureBootSVN -BootManagerPath "D:\Recovery\bootmgfw.efi"
```

This command checks the SVN of the specified boot manager file and compares it against the system’s firmware and staged SVN requirements.

## PARAMETERS

### -BootManagerPath
Specifies the full path to a boot manager `.EFI` file to evaluate.  
The cmdlet reads the SVN from the specified file and compares it to the system’s firmware and staged SVN values.

```yaml
Type: String
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
Parameter Sets: (All)

Position: Named
Mandatory: False
Value from pipeline: False
Value from pipeline by property name: False
Value from remaining arguments: False
```

## Outputs
This cmdlet returns a SecureBootSVNInfo object with the following properties: 

- **FirmwareSVN – The current SVN requirement enforced by the UEFI firmware.**
- **BootManagerSVN – The SVN of the currently installed or specified boot manager.**
- **StagedSVN – The SVN of any pending Secure Boot update installed on the system and not yet applied to the firmware.**
- **ComplianceStatus – Indicates whether the boot manager meets the firmware’s SVN requirement.**
- **BootManagerPath – (Optional) The path to the boot manager file tested, if specified.**

## Notes 

- This cmdlet is read-only and does not modify any firmware or system settings.
- On systems without Secure Boot or UEFI support, the cmdlet returns an error or empty output.
- The cmdlet must be run from an elevated PowerShell session. 

## Related Links 

[Confirm-SecureBootUEFI](./Confirm-SecureBootUEFI.md)

[Format-SecureBootUEFI](./Format-SecureBootUEFI.md)

[Get-SecureBootPolicy](./Get-SecureBootPolicy.md)

[Get-SecureBootUEFI](./Get-SecureBootUEFI.md)

[Monitoring Secure Boot certificate status with Microsoft Intune remediations](https://support.microsoft.com/en-us/topic/monitoring-secure-boot-certificate-status-with-microsoft-intune-remediations-6696a27b-fa09-4570-b112-124965adc87f)

[Secure Boot Certificate Updates for Azure Virtual Desktop](https://support.microsoft.com/en-us/topic/secure-boot-certificate-updates-for-azure-virtual-desktop-06a8a1bc-2510-4ead-9bea-3698e1d6b1db)






















