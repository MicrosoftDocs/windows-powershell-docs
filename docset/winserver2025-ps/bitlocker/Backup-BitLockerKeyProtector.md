---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BitLocker-help.xml
Module Name: BitLocker
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/bitlocker/backup-bitlockerkeyprotector?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Backup-BitLockerKeyProtector
---

# Backup-BitLockerKeyProtector

## SYNOPSIS
Saves a key protector for a BitLocker volume in AD DS.

## SYNTAX

```
Backup-BitLockerKeyProtector [-MountPoint] <String[]> [-KeyProtectorId] <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Backup-BitLockerKeyProtector** cmdlet saves a recovery password key protector for a volume protected by BitLocker Drive Encryption to Active Directory Domain Services (AD DS).
Specify a key to be saved by ID.

For an overview of BitLocker, see [BitLocker Drive Encryption Overview](https://technet.microsoft.com/en-us/library/cc732774.aspx) on TechNet.

## EXAMPLES

### Example 1: Save a key protector for a volume
```
PS C:\> $BLV = Get-BitLockerVolume -MountPoint "C:"
PS C:\> Backup-BitLockerKeyProtector -MountPoint "C:" -KeyProtectorId $BLV.KeyProtector[1].KeyProtectorId
```

This example saves a key protector for a specified BitLocker volume.

The first command uses **Get-BitLockerVolume** to obtain a BitLocker volume and store it in the $BLV variable.

The second command backs up the key protector for the BitLocker volume specified by the *MountPoint* parameter.
The command specifies the key protector by using its ID, contained in the BitLocker object stored in $BLV.
The **KeyProtector** attribute contains an array of key protectors associated to the volume.
This command uses standard array syntax to index the **KeyProtector** object.
The key protector that corresponds to the recovery password key protector can be identified by using the **KeyProtectorType** attribute in the **KeyProtector** object.

### Example 2: Save a key protector using an ID
```
PS C:\> Backup-BitLockerKeyProtector -MountPoint "C:" -KeyProtectorId "{E2611001E-6AD0-4A08-BAAA-C9c031DB2AA6}"
```

This command saves a key protector for a specified BitLocker volume to AD DS.
The command specifies the key protector by using its ID.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyProtectorId
Specifies the ID for a key protector or a **KeyProtector** object.
A BitLocker volume object includes a **KeyProtector** object.
You can specify the key protector object itself, or you can specify the ID.
See the Examples section.
To obtain a BitLocker volume object, use the **Get-BitLockerVolume** cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -MountPoint
Specifies an array of drive letters or BitLocker volume objects.
The cmdlet saves key protectors for the volumes specified.
To obtain a BitLocker volume object, use the **Get-BitLockerVolume** cmdlet.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### BitLockerVolume, String

## OUTPUTS

### BitLockerVolume

## NOTES

## RELATED LINKS

[Add-BitLockerKeyProtector](./Add-BitLockerKeyProtector.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

[Remove-BitLockerKeyProtector](./Remove-BitLockerKeyProtector.md)

