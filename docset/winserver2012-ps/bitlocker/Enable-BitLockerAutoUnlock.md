---
external help file: Bitlocker_Cmdlets.xml
Module Name: BitLocker
online version: https://learn.microsoft.com/powershell/module/bitlocker/enable-bitlockerautounlock?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Enable-BitLockerAutoUnlock

## SYNOPSIS
Enables automatic unlocking for a BitLocker volume.

## SYNTAX

```
Enable-BitLockerAutoUnlock [-MountPoint] <String[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Enable-BitLockerAutoUnlock** cmdlet enables automatic unlocking for a volume protected by BitLocker Disk Encryption.

You can configure BitLocker to automatically unlock volumes that do not host an operating system.
After a user unlocks the operating system volume, BitLocker uses encrypted information stored in the registry and volume metadata to unlock any data volumes that use automatic unlocking.

For an overview of BitLocker, see BitLocker Drive Encryption Overviewhttp://technet.microsoft.com/en-us/library/cc732774.aspx (http://technet.microsoft.com/en-us/library/cc732774.aspx) on TechNet.

## EXAMPLES

### Example 1: Enable automatic unlocking
```
PS C:\>Enable-BitLockerAutoUnlock -MountPoint "E:"
```

This command enables automatic unlocking for the specified BitLocker volume.

## PARAMETERS

### -MountPoint
Specifies an array of drive letters or BitLocker volume objects.
The cmdlet enables automatic unlocking for the volumes specified.
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

[Clear-BitLockerAutoUnlock](./Clear-BitLockerAutoUnlock.md)

[Disable-BitLockerAutoUnlock](./Disable-BitLockerAutoUnlock.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

