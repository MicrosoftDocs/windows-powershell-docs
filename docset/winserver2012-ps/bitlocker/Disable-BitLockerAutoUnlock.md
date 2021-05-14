---
external help file: Bitlocker_Cmdlets.xml
Module Name: BitLocker
online version: https://docs.microsoft.com/powershell/module/bitlocker/disable-bitlockerautounlock?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Disable-BitLockerAutoUnlock

## SYNOPSIS
Disables automatic unlocking for a BitLocker volume.

## SYNTAX

```
Disable-BitLockerAutoUnlock [-MountPoint] <String[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Disable-BitLockerAutoUnlock** cmdlet disables automatic unlocking for a volume protected by BitLocker Disk Encryption.
The cmdlet removes automatic unlocking keys for specified volumes stored on a volume that hosts an operating system.

You can configure BitLocker to automatically unlock volumes that do not host an operating system.
After a user unlocks the operating system volume, BitLocker uses encrypted information stored in the registry and volume metadata to access data volumes that use automatic unlocking.

You can specify a volume by drive letter, or you can specify a BitLocker volume object.
You must remove automatic unlocking keys before you can disable BitLocker by using the Disable-BitLocker cmdlet.
You can use the Clear-BitLockerAutoUnlock cmdlet to remove keys for all the volumes configured to use automatic unlocking instead of just specified volumes.

For an overview of BitLocker, see BitLocker Drive Encryption Overviewhttp://technet.microsoft.com/en-us/library/cc732774.aspx (http://technet.microsoft.com/en-us/library/cc732774.aspx) on TechNet.

## EXAMPLES

### Example 1: Disable automatic unlocking for a volume
```
PS C:\> Disable-AutoUnlock -MountPoint "E:"
```

This command disables automatic unlocking for the specified BitLocker volume.

## PARAMETERS

### -MountPoint
Specifies an array of drive letters or BitLocker volume objects.
The cmdlet disables automatic unlocking for the volumes specified.
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

[Enable-BitLockerAutoUnlock](./Enable-BitLockerAutoUnlock.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

