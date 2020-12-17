---
external help file: BitLocker-help.xml
Module Name: BitLocker
online version: 
schema: 2.0.0
title: Remove-BitLockerKeyProtector
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 09CDDA63-9E82-44F0-8755-878974B0010B
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
To add a protector, use the Add-BitLockerKeyProtector cmdlet.

If you remove all the key protectors for a BitLocker volume, BitLocker stores the data encryption key for the volume without using encryption.
This means that any user that can access the volume can read the encrypted data on the volume unless you add a key protector.
Any encrypted data on the drive remains encrypted.

We recommend you have at least one recovery password as key protector to a volume in case you need to recover a system.

For an overview of BitLocker, see BitLocker Drive Encryption Overviewhttp://technet.microsoft.com/en-us/library/cc732774.aspx (http://technet.microsoft.com/en-us/library/cc732774.aspx) on TechNet.

## EXAMPLES

### Example 1: Remove a key protector for a volume
```
PS C:\> $BLV = Get-BitLockerVolume -MountPoint "C:"
Remove-BitlockerKeyProtector -MountPoint "C:" -KeyProtectorId $BLV.KeyProtector[1]
```

This example removes a key protector for a specified BitLocker volume.

The first command uses Get-BitLockerVolume to obtain a BitLocker volume and store it in the $BLV variable.

The second command removes the key protector for the BitLocker volume specified by the **MountPoint** parameter.
The command specifies the key protector by using its ID, contained in the BitLocker object stored in $BLV.

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
To obtain a BitLocker volume object, use the Get-BitLockerVolume cmdlet.

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
To obtain a BitLocker volume object, use the Get-BitLockerVolume cmdlet.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### BitLockerVolume[], String[]

## OUTPUTS

### BitLockerVolume[]

## NOTES

## RELATED LINKS

[Add-BitLockerKeyProtector](./Add-BitLockerKeyProtector.md)

[Backup-BitLockerKeyProtector](./Backup-BitLockerKeyProtector.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

