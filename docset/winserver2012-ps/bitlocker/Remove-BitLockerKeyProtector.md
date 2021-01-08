---
external help file: Bitlocker_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 09CDDA63-9E82-44F0-8755-878974B0010B
manager: dansimp
---

# Remove-BitLockerKeyProtector

## SYNOPSIS
Removes a key protector for a BitLocker volume.

## SYNTAX

```
Remove-BitLockerKeyProtector [-MountPoint] <String[]> [-KeyProtectorId] <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-BitLockerKeyProtector** cmdlet removes a key protector for a volume protected by BitLocker Drive Encryption.

You can specify a key protector to remove by using an ID.
To add a protector, use the **Add-BitLockerKeyProtector** cmdlet.

If you remove all the key protectors for a BitLocker volume, BitLocker stores the data encryption key for the volume without using encryption.
This means that any user that can access the volume can read the encrypted data on the volume unless you add a key protector.
Any encrypted data on the drive remains encrypted.

We recommend you have at least one recovery password as key protector to a volume in case you need to recover a system.

For an overview of BitLocker, see [BitLocker Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-8.1-and-8/dn641993(v=ws.11)).

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

The second command filters the key protectors to get only the one with TpmPin type and stores it in `$TpmPinKeyProtector` varible.

The third command removes they key protector by its ID.

## PARAMETERS

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
Position: 2
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
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
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### BitLockerVolume[], String[]

## OUTPUTS

### BitLockerVolume[]

## NOTES

## RELATED LINKS

[Add-BitLockerKeyProtector](./Add-BitLockerKeyProtector.md)

[Backup-BitLockerKeyProtector](./Backup-BitLockerKeyProtector.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

