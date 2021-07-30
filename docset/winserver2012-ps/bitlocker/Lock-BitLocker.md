---
external help file: Bitlocker_Cmdlets.xml
Module Name: BitLocker
online version: https://docs.microsoft.com/powershell/module/bitlocker/lock-bitlocker?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Lock-BitLocker

## SYNOPSIS
Prevents access to encrypted data on a BitLocker volume.

## SYNTAX

```
Lock-BitLocker [-MountPoint] <String[]> [-ForceDismount] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Lock-BitLocker** cmdlet prevents access to all encrypted data on a volume that uses BitLocker Drive Encryption.
You can use the Unlock-BitLocker cmdlet to restore access.

You can specify a volume to lock by drive letter, or you can specify a BitLocker volume object.
This cmdlet cannot lock a volume that hosts the operating system.
If you attempt to lock an already locked volume, this cmdlet does nothing.

For an overview of BitLocker, see BitLocker Drive Encryption Overviewhttps://technet.microsoft.com/en-us/library/cc732774.aspx (https://technet.microsoft.com/en-us/library/cc732774.aspx) on TechNet.

## EXAMPLES

### Example 1: Lock a volume
```
PS C:\> Lock-Volume -MountPoint "E:" -ForceDismount
```

This command locks the BitLocker volume specified with the **Mount** parameter.
The command uses the **ForceDismount** parameter, so the cmdlet attempts to lock the volume even if it is in use.

## PARAMETERS

### -ForceDismount
Indicates that the cmdlet attempts to lock a drive even if the drive is in use.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: fd

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -MountPoint
Specifies an array of drive letters or BitLocker volume objects.
The cmdlet attempts to lock the volumes specified.
To obtain a BitLocker volume object, use the Get-BitLockerVolume cmdlet.

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

[Disable-BitLocker](./Disable-BitLocker.md)

[Enable-BitLocker](./Enable-BitLocker.md)

[Resume-BitLocker](./Resume-BitLocker.md)

[Suspend-BitLocker](./Suspend-BitLocker.md)

[Unlock-BitLocker](./Unlock-BitLocker.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

