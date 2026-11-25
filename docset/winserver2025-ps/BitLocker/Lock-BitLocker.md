---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BitLocker-help.xml
Module Name: BitLocker
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/bitlocker/lock-bitlocker?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Lock-BitLocker
---

# Lock-BitLocker

## SYNOPSIS
Prevents access to encrypted data on a BitLocker volume.

## SYNTAX

```
Lock-BitLocker [-MountPoint] <String[]> [-ForceDismount] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Lock-BitLocker** cmdlet prevents access to all encrypted data on a volume that uses BitLocker Drive Encryption.
You can use the **Unlock-BitLocker** cmdlet to restore access.

You can specify a volume to lock by drive letter, or you can specify a BitLocker volume object.
This cmdlet cannot lock a volume that hosts the operating system.
If you attempt to lock an already locked volume, this cmdlet does nothing.

For an overview of BitLocker, see [BitLocker Drive Encryption Overview](https://technet.microsoft.com/en-us/library/cc732774.aspx) on TechNet.

## EXAMPLES

### Example 1: Lock a volume
```
PS C:\> Lock-BitLocker -MountPoint "E:" -ForceDismount
```

This command locks the BitLocker volume specified with the *MountPoint* parameter.
The command uses the *ForceDismount* parameter, so the cmdlet attempts to lock the volume even if it is in use.

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

### -ForceDismount
Indicates that the cmdlet attempts to lock a drive even if the drive is in use.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: fd

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MountPoint
Specifies an array of drive letters or BitLocker volume objects.
The cmdlet attempts to lock the volumes specified.
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

### BitLockerVolume[], String[]

## OUTPUTS

### BitLockerVolume[]

## NOTES

## RELATED LINKS

[Disable-BitLocker](./Disable-BitLocker.md)

[Enable-BitLocker](./Enable-BitLocker.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

[Resume-BitLocker](./Resume-BitLocker.md)

[Suspend-BitLocker](./Suspend-BitLocker.md)

[Unlock-BitLocker](./Unlock-BitLocker.md)

