---
external help file: Bitlocker_Cmdlets.xml
Module Name: BitLocker
online version: https://learn.microsoft.com/powershell/module/bitlocker/suspend-bitlocker?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Suspend-BitLocker

## SYNOPSIS
Suspends Bitlocker encryption for the specified volume.

## SYNTAX

```
Suspend-BitLocker [-MountPoint] <String[]> [[-RebootCount] <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Suspend-BitLocker** cmdlet suspends Bitlocker encryption, allowing users to access encrypted data on a volume that uses BitLocker Drive Encryption.
This cmdlet makes the encryption key available in the clear.

Suspension of BitLocker does not mean that BitLocker decrypts data on the volume.
Instead, suspension makes key used to decrypt the data available to everyone in the clear.
New data written to the disk is still encrypted.

While suspended, BitLocker does not validate system integrity at start up.
You might suspend BitLocker protection for firmware upgrades or system updates.

You can specify the number of times that a computer restarts before the BitLocker suspension ends by using the **RebootCount** parameter, or you can use the Resume-BitLocker cmdlet to manually resume protection.
If you do not specify the **RebootCount** parameter, the cmdlet uses a value of one (1), so BitLocker protection resumes after the next restart.

For an overview of BitLocker, see BitLocker Drive Encryption Overviewhttp://technet.microsoft.com/en-us/library/cc732774.aspx (http://technet.microsoft.com/en-us/library/cc732774.aspx) on TechNet.

## EXAMPLES

### Example 1: Suspend BitLocker protection
```
PS C:\> Suspend-BitLocker -MountPoint "C:" -RebootCount 0
```

This command suspends Bitlocker encryption on the BitLocker volume specified by the **MountPoint** parameter.
Because the **RebootCount** parameter value is 0, BitLocker encryption remains suspended until you run the Resume-BitLocker cmdlet.

## PARAMETERS

### -MountPoint
Specifies an array of drive letters or BitLocker volume objects.
This cmdlet suspends protection for the volumes specified.
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

### -RebootCount
Specifies the number of computer restarts before BitLocker restores protection.
The acceptable values for this parameter are:integers from 0 to 15.
Specify zero to suspend protection indefinitely until you resume it by using the Resume-BitLocker cmdlet.

If you do not include this parameter, the cmdlet uses a value of one.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: 0
Accept pipeline input: False
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

[Resume-BitLocker](./Resume-BitLocker.md)

[Unlock-BitLocker](./Unlock-BitLocker.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

