---
external help file: WSBackup_Cmdlets.xml
Module Name: WindowsServerBackup
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/get-wbsystemstate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WBSystemState

## SYNOPSIS
Gets a Boolean value that indicates whether system state recovery was added to the backup policy.

## SYNTAX

```
Get-WBSystemState [-Policy] <WBPolicy>
```

## DESCRIPTION
The **Get-WBSystemState** cmdlet gets a Boolean value that indicates whether the ability to perform system state recoveries along with the backups was added to the **WBPolicy** object.
If the system state is not in the list of items to be backed up, use the Add-WBSystemState cmdlet to add it to the list.

To use this or any other Windows Server 2012 Backup cmdlets, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get the system state setting from the backup
```
PS C:\>$Policy = Get-WBPolicy PS C:\> Get-WBSystemState -Policy $Policy
```

This example displays a Boolean value that indicates whether the system state setting was added to the **WBPolicy** object **$Policy**.
The system state setting enables you to use the backups to perform system state recoveries.

The first command stores the result of the **Get-WBPolicy** cmdlet to the variable named **$Policy**

The second command displays the result of the **Get-WBSystemState** cmdlet using the variable named **$Policy**.

## PARAMETERS

### -Policy
Specifies a **WBPolicy** object that contains the backup policy to display.

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
The Get-WBSystemState cmdlet queries the **WBPolicy** object for the backup policy.

## OUTPUTS

### boolean
The Get-WBSystemState cmdlet displays a Boolean value to indicate whether the system state is included in the WBPolicy object.

## NOTES

## RELATED LINKS

[Add-WBSystemState](./Add-WBSystemState.md)

[New-WBPolicy](./New-WBPolicy.md)

[Remove-WBSystemState](./Remove-WBSystemState.md)

