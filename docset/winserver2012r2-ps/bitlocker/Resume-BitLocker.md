---
external help file: BitLocker-help.xml
Module Name: BitLocker
online version: 
schema: 2.0.0
title: Resume-BitLocker
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
ms.assetid: 18BE9A1F-283D-448F-A68F-D0450FCAB515
---

# Resume-BitLocker

## SYNOPSIS
Restores Bitlocker encryption for the specified volume.

## SYNTAX

```
Resume-BitLocker [-MountPoint] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Resume-BitLocker** cmdlet restores encryption on a volume that uses BitLocker Drive Encryption.
You can use the Suspend-BitLocker cmdlet to allow users to access encrypted data temporarily.
Data written to the volume continues to be encrypted, but the key to unlock the operating system volume is in the open.

You can specify a volume by drive letter, or you can specify a BitLocker volume object.
If you specify a BitLocker volume that is not suspended, this cmdlet has no effect on that volume.

For an overview of BitLocker, see BitLocker Drive Encryption Overviewhttp://technet.microsoft.com/en-us/library/cc732774.aspx (http://technet.microsoft.com/en-us/library/cc732774.aspx) on TechNet.

## EXAMPLES

### Example 1: Resume protection for a volume
```
PS C:\> Resume-BitLocker -MountPoint "C:"
```

This command resumes BitLocker protection for the C: drive.

### Example 2: Resume protection for all volumes on a computer
```
PS C:\>Get-BitLockerVolume | Resume-BitLocker
```

This command gets all the BitLocker volumes for the current computer by using the Get-BitLockerVolume cmdlet and passes them to Resume-BitLocker by using the pipe operator.
The command restores protection for all BitLocker volumes.

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
This cmdlet resumes protection for the volumes specified.
To obtain a BitLocker volume object, use theGet-BitLockerVolume cmdlet.

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

[Disable-BitLocker](./Disable-BitLocker.md)

[Enable-BitLocker](./Enable-BitLocker.md)

[Lock-BitLocker](./Lock-BitLocker.md)

[Suspend-BitLocker](./Suspend-BitLocker.md)

[Unlock-BitLocker](./Unlock-BitLocker.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

