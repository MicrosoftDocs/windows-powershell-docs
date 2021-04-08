---
author: Kateyanne
external help file: WSBackup_Cmdlets.xml
manager: dansimp
Module Name: WindowsServerBackup
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/windowsserverbackup/get-wbbackuptarget?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WBBackupTarget

## SYNOPSIS
Gets backup storage locations that you specified as part of a backup policy.

## SYNTAX

```
Get-WBBackupTarget [-Policy] <WBPolicy>
```

## DESCRIPTION
The **Get-WBBackupTarget** cmdlet gets backup storage locations that you specified for a **WBPolicy** object that contains a backup policy.
Valid locations include disks, volumes, or remote shared folders.
To view the list of all online disks, use the Get-WBDisk cmdlet.

You can add the locations that the cmdlet returns to a **WBPolicy** object by specifying them as backup storage locations to the New-WBBackupTarget cmdlet.

To use Windows Server® 2012 Backup cmdlets, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get a list of backup targets
```
PS C:\>$Policy = Get-WBPolicy PS C:\> Get-WBBackupTarget -Policy $Policy
```

This example gets a list of the storage backup locations from a backup policy.

The first command gets the current backup policy and stores it in a variable named **$Policy**.

The second command gets the list of storage backup locations from the **WBPolicy** object that is stored in the **$Policy** variable.

## PARAMETERS

### -Policy
Specifies a backup policy object for which to display information.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases: InPolicy

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### WBPolicy
The Get-WBBackupTarget cmdlet queries the backup policy contained in the specified **WBPolicy** object.

## OUTPUTS

### WBBackupTarget []
The Get-WBBackupTarget cmdlet displays a list of the storage locations that the backup policy object contains.

## NOTES

## RELATED LINKS

[Add-WBBackupTarget](./Add-WBBackupTarget.md)

[Get-WBDisk](./Get-WBDisk.md)

[Get-WBPolicy](./Get-WBPolicy.md)

[New-WBBackupTarget](./New-WBBackupTarget.md)

[Remove-WBBackupTarget](./Remove-WBBackupTarget.md)

