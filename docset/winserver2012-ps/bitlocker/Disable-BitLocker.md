---
external help file: Bitlocker_Cmdlets.xml
Module Name: BitLocker
online version: https://docs.microsoft.com/powershell/module/bitlocker/disable-bitlocker?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Disable-BitLocker

## SYNOPSIS
Disables BitLocker encryption for a volume.

## SYNTAX

```
Disable-BitLocker [-MountPoint] <String[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Disable-BitLocker** cmdlet disables BitLocker Drive Encryption for a BitLocker volume.
When you run this cmdlet, it removes all key protectors and begins decrypting the content of the volume.

If the volume that hosts the operating system contains any automatic unlocking keys, the cmdlet does not proceed.
You can use the Clear-BitLockerAutoUnlock cmdlet to remove all automatic unlocking keys.
Then you can disable BitLocker for the volume.

For an overview of BitLocker, see BitLocker Drive Encryption Overviewhttps://technet.microsoft.com/en-us/library/cc732774.aspx (https://technet.microsoft.com/en-us/library/cc732774.aspx) on TechNet.

## EXAMPLES

### Example 1: Disable BitLocker for a volume
```
PS C:\> Disable-BitLocker -MountPoint "C:"
```

This command disables BitLocker for the specified BitLocker volume.
BitLocker begins decrypting data on C: immediately.

### Example 2: Disable BitLocker for all volumes
```
PS C:\>$BLV = Get-BitLockerVolume PS C:\>Disable-BitLocker -MountPoint $BLV
```

This example disables BitLocker encryption for all volumes.

The first command uses Get-BitLockerVolume to get all the BitLocker volumes for the current computer and stores them in the $BLV variable.

The second command disables BitLocker encryption for all the BitLocker volumes stored in the $BLV variable.
BitLocker begins decrypting data on the volumes.

## PARAMETERS

### -MountPoint
Specifies an array of drive letters or BitLocker volume objects.
The cmdlet disables protection for the volumes specified.
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

[Enable-BitLocker](./Enable-BitLocker.md)

[Lock-BitLocker](./Lock-BitLocker.md)

[Resume-BitLocker](./Resume-BitLocker.md)

[Suspend-BitLocker](./Suspend-BitLocker.md)

[Unlock-BitLocker](./Unlock-BitLocker.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

