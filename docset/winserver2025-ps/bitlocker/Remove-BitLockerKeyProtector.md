---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BitLocker-help.xml
Module Name: BitLocker
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/bitlocker/remove-bitlockerkeyprotector?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-BitLockerKeyProtector
---

# Remove-BitLockerKeyProtector

## SYNOPSIS
Removes a key protector for a BitLocker volume.

## SYNTAX

```
Remove-BitLockerKeyProtector [-MountPoint] <String[]> [-KeyProtectorId] <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-BitLockerKeyProtector** cmdlet removes a key protector for a volume protected by BitLocker Drive Encryption.

You can specify a key protector to remove by using an ID.
To add a protector, use the **Add-BitLockerKeyProtector** cmdlet.

If you remove all the key protectors for a BitLocker volume, BitLocker stores the data encryption key for the volume without using encryption.
This means that any user that can access the volume can read the encrypted data on the volume unless you add a key protector.
Any encrypted data on the drive remains encrypted.

We recommend you have at least one recovery password as key protector to a volume in case you need to recover a system.

For an overview of BitLocker, see [Overview of BitLocker Device Encryption](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10).

## EXAMPLES

### Example 1: Remove the second key protector for a volume
```powershell
PS C:\> $BLV = Get-BitLockerVolume -MountPoint "C:"
PS C:\> Remove-BitLockerKeyProtector -MountPoint "C:" -KeyProtectorId $BLV.KeyProtector[1].KeyProtectorId
```

This example removes a key protector for a specified BitLocker volume.

The first command uses **Get-BitLockerVolume** to obtain a BitLocker volume and store it in the `$BLV` variable.

The second command removes the key protector for the BitLocker volume specified by the **MountPoint** parameter.
The command specifies the key protector by using its ID, contained in the BitLocker object stored in `$BLV`.

### Example 2: Remove TpmPin key protector for a volume
```powershell
PS C:\> $BLV = Get-BitlockerVolume -MountPoint "C:"
PS C:\> $TpmPinKeyProtector = $BLV.KeyProtector | Where-Object {$PSItem.KeyProtectorType -eq "TpmPin"}
PS C:\> Remove-BitLockerKeyProtector -MountPoint "C:" -KeyProtectorId $TpmPinKeyProtector.KeyProtectorId
```

This example removes a key protector of type TpmPin for a specified BitLocker Volume.

The first command uses **Get-BitLockerVolume** to obtain a BitLocker volume and store it in the `$BLV` variable.

The second command filters the key protectors to get only the one with TpmPin type and stores it in the `$TpmPinKeyProtector` variable.

The third command removes the key protector by its ID.

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
Specifies the ID for a key protector.
A BitLocker volume object includes a **KeyProtector** object.
You have to specify the key protector ID.
See the Examples section.
To obtain a BitLocker volume object, use the **Get-BitLockerVolume** cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: id

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -MountPoint
Specifies an array of drive letters or BitLocker volume objects.
The cmdlet removes key protectors for the volumes specified.
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
This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### BitLockerVolume[], String[]

## OUTPUTS

### BitLockerVolume[]

## NOTES

## RELATED LINKS

[Add-BitLockerKeyProtector](./Add-BitLockerKeyProtector.md)

[Backup-BitLockerKeyProtector](./Backup-BitLockerKeyProtector.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)
