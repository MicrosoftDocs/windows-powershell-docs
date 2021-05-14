---
external help file: Bitlocker_Cmdlets.xml
Module Name: BitLocker
online version: https://docs.microsoft.com/powershell/module/bitlocker/resume-bitlocker?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Resume-BitLocker

## SYNOPSIS
Restores Bitlocker encryption for the specified volume.

## SYNTAX

```
Resume-BitLocker [-MountPoint] <String[]> [-Confirm] [-WhatIf]
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

### -MountPoint
Specifies an array of drive letters or BitLocker volume objects.
This cmdlet resumes protection for the volumes specified.
To obtain a BitLocker volume object, use theGet-BitLockerVolume cmdlet.

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

[Lock-BitLocker](./Lock-BitLocker.md)

[Suspend-BitLocker](./Suspend-BitLocker.md)

[Unlock-BitLocker](./Unlock-BitLocker.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

