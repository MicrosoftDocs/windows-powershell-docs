---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/add-wbfilespec?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WBFileSpec
---

# Add-WBFileSpec

## SYNOPSIS
Adds a backup file specification to a backup policy.

## SYNTAX

```
Add-WBFileSpec [-Policy] <WBPolicy> [-FileSpec] <WBFileSpec[]> [<CommonParameters>]
```

## DESCRIPTION
The **Add-WBFileSpec** cmdlet adds a backup file specification, which specifies the items to include in or exclude from a backup, to a backup policy.
A **WBFileSpec** object contains the backup file specification, and a **WBPolicy** object contains the backup policy.
The **WBFileSpec** object can include or exclude multiple files, folders, or volumes.
You can create a list of items to include or exclude by using the [New-WBFileSpec](./New-WBFileSpec.md) cmdlet and then using the **Add-WBFileSpec** cmdlet to update the **WBPolicy** object.

Before you can add a backup file specification to a **WBPolicy** object, you must put the **WBPolicy** object in edit mode.
To put the **WBPolicy** object in edit mode for a policy that you set as the scheduled backup policy, use the Get-WBPolicy cmdlet with the *Editable* parameter.
The [New-WBPolicy](./New-WBPolicy.md) cmdlet creates a new **WBPolicy** object that is already in edit mode.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Add backup file specifications to a backup policy
```
PS C:\> $Filespec1 = New-WBFileSpec -FileSpec C:\Sample\1.jpg
PS C:\> $Filespec2 = New-WBFileSpec -FileSpec C:\Sample\*.txt
PS C:\> $Filespec3 = New-WBFileSpec -FileSpec C:\Sample\*.mp3 -Exclude
PS C:\> Add-WBFileSpec -Policy $Policy $Filespec1,$Filespec2,$Filespec3
```

This example adds three backup file specifications to the **WBPolicy** object in the variable named $Policy.

The first command assigns the file named C:\sample\1.jpg to the variable named $Filespec1.

The second command assigns the files that match the wildcard specification C:\Sample\*.txt (text files in the C:\Sample directory) to the variable named $Filespec2.

The third command assigns the files that match the wildcard specification C:\Sample\*.mp3 txt (MP3 files in the C:\Sample directory) to the variable named $Filespec3.
Because this command includes the *Exclude* parameter, the backup from this policy excludes MP3 files in C:\Sample.

The fourth command adds the file specifications in $Filespec1,  $Filespec2, and $Filespec3 to the backup policy in the variable named $Policy.

### Example 2: Add an array of backup file specifications to a backup policy
```
PS C:\> $Filespecarray = ($Filespec1, $Filespec2, $Filespec3)
PS C:\> Add-WBFileSpec -Policy $Policy $Filespecarray
```

This example adds an array of backup file specifications to a backup policy.

The first command assigns the file specifications in the variables named $Filespec1, $Filespec2, and $Filespec3 to the array in the variable named $Filespecarray.

The second command adds the array of file specifications in $Filespecarray to the **WBPolicy** object in the variable named $Policy.

## PARAMETERS

### -FileSpec
Specifies an array of **WBFileSpec** objects that contain backup file specifications to add to the **WBPolicy** object.

```yaml
Type: WBFileSpec[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Policy
Specifies a **WBPolicy** object that contains the backup policy to update.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.ServerBackup.Commands.WBPolicy

### Microsoft.Windows.ServerBackup.Commands.WBFileSpec[]

This cmdlet adds a list of items from a **WBFileSpec** object that contains a backup file specification to a **WBPolicy** object that contains a backup policy.

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Get-WBFileSpec](./Get-WBFileSpec.md)

[New-WBFileSpec](./New-WBFileSpec.md)

[New-WBPolicy](./New-WBPolicy.md)

[Remove-WBFileSpec](./Remove-WBFileSpec.md)

