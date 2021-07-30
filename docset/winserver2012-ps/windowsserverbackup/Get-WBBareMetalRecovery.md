---
external help file: WSBackup_Cmdlets.xml
Module Name: WindowsServerBackup
online version: https://docs.microsoft.com/powershell/module/windowsserverbackup/get-wbbaremetalrecovery?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WBBareMetalRecovery

## SYNOPSIS
Indicates whether or not a backup policy can perform bare metal recoveries from backups.

## SYNTAX

```
Get-WBBareMetalRecovery [-Policy] <WBPolicy>
```

## DESCRIPTION
The **Get-WBBareMetalRecovery** cmdlet gets a Boolean value that indicates whether or not a **WBPolicy** object that contains a backup policy can perform bare metal recoveries from backups.
A bare metal recovery is the process of rebuilding a computer after a catastrophic failure.
The recovery process backs up the system volume and master boot record by copying the entire volume and using Volume Shadow Copy Service (VSS) writers to ensure that all applications are in a consistent state for the copy.
For more information about bare metal recovery, see Backup for Bare Metal Recoveryhttps://technet.microsoft.com/en-us/library/bb795820.aspx (https://technet.microsoft.com/en-us/library/bb795820.aspx) on TechNet.

If a policy does not include the ability to perform bare metal recoveries from backups, use the Add-WBBareMetalRecovery cmdlet to add this ability.

To use Windows Server® 2012 Backup cmdlets, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Determine whether a backup policy includes bare metal recovery
```
PS C:\> Get-WBBareMetalRecovery -Policy $Policy
```

This command gets a Boolean value that indicates whether bare metal recovery is set in the **WBPolicy** object and stores this value in the variable named **$Policy**.

## PARAMETERS

### -Policy
Specifies a **WBPolicy** object that contains the backup policy for which to display information.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### WBPolicy
The Get-WBBareMetalRecovery cmdlet queries a **WBPolicy** object that contains a backup policy to determine whether the server can use backups that use that policy for bare metal recovery.

## OUTPUTS

### Boolean
The Get-WBBareMetalRecovery cmdlet displays a Boolean value to indicate whether the server can run backups that use a specified policy for bare metal recovery.

## NOTES

## RELATED LINKS

[Add-WBBareMetalRecovery](./Add-WBBareMetalRecovery.md)

[Remove-WBBareMetalRecovery](./Remove-WBBareMetalRecovery.md)

