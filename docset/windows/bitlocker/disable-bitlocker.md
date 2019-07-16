---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BitLocker-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Disable-BitLocker
ms.reviewer:
ms.assetid: C47D89E1-C414-4523-B8C7-4F4297E21716
---

# Disable-BitLocker

## SYNOPSIS
Disables BitLocker Drive Encryption for a volume.

## SYNTAX

```
Disable-BitLocker [-MountPoint] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-BitLocker** cmdlet disables BitLocker Drive Encryption for a BitLocker volume.
When you run this cmdlet, it removes all key protectors and begins decrypting the content of the volume.

If the volume that hosts the operating system contains any automatic unlocking keys, the cmdlet does not proceed.
You can use the **Clear-BitLockerAutoUnlock** cmdlet to remove all automatic unlocking keys.
Then you can disable BitLocker for the volume.

For an overview of BitLocker, see [BitLocker Drive Encryption Overview](http://technet.microsoft.com/en-us/library/cc732774.aspx) on TechNet.

## EXAMPLES

### Example 1: Disable BitLocker for a volume
```
PS C:\> Disable-BitLocker -MountPoint "C:"
```

This command disables BitLocker for the specified BitLocker volume.
BitLocker begins decrypting data on C: immediately.

### Example 2: Disable BitLocker for all volumes
```
PS C:\>$BLV = Get-BitLockerVolume
PS C:\>Disable-BitLocker -MountPoint $BLV
```

This example disables BitLocker encryption for all volumes.

The first command uses **Get-BitLockerVolume** to get all the BitLocker volumes for the current computer and stores them in the $BLV variable.

The second command disables BitLocker encryption for all the BitLocker volumes stored in the $BLV variable.
BitLocker begins decrypting data on the volumes.

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

### -MountPoint
Specifies an array of drive letters or BitLocker volume objects.
The cmdlet disables protection for the volumes specified.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### BitLockerVolume[], String[]

## OUTPUTS

### BitLockerVolume[]

## NOTES

## RELATED LINKS

[Enable-BitLocker](./Enable-BitLocker.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

[Lock-BitLocker](./Lock-BitLocker.md)

[Resume-BitLocker](./Resume-BitLocker.md)

[Suspend-BitLocker](./Suspend-BitLocker.md)

[Unlock-BitLocker](./Unlock-BitLocker.md)

