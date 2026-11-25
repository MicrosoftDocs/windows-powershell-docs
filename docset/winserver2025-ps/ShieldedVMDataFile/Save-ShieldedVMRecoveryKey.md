---
external help file: Microsoft.Windows.HardenedFabric.Cmdlets.dll-Help.xml
Module Name: ShieldedVMDataFile
online version: https://learn.microsoft.com/powershell/module/shieldedvmdatafile/save-shieldedvmrecoverykey?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Save-ShieldedVMRecoveryKey
---

# Save-ShieldedVMRecoveryKey

## SYNOPSIS
Extracts the encrypted BitLocker recovery key from a shielded virtual machine's operating system disk.

## SYNTAX

### VHDParameterSet (Default)
```
Save-ShieldedVMRecoveryKey -VHDPath <String> -Path <String> [-Force] [-WhatIf] [-Confirm]
```

### DiskNumberParameterSet
```
Save-ShieldedVMRecoveryKey -DiskNumber <Int32> -Path <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
The *Save-ShieldedVMRecoveryKey* cmdlet is used to extract the encrypted BitLocker recovery key from a shielded virtual machine's operaing system disk.
The key can be obtained from an offline VHDX or an online, mounted disk.
The encrypted recovery key can be passed to the [Unprotect-ShieldedVMRecoveryKey](Unprotect-ShieldedVMRecoveryKey.md) cmdlet to decrypt the recovery key.

This cmdlet only works with Windows shielded VMs created with a shielding data file created on Windows Server, version 1709 or newer.

## EXAMPLES

### Example 1
```
PS C:\> Save-ShieldedVMRecoveryKey -VHDPath 'C:\temp\MyShieldedVM.vhdx' -Path 'C:\temp\MyShieldedVMEncryptedRecoveryKey.ebek'
```

Extracts the encrypted recovery key from the "MyShieldedVM.vhdx" file and saves it to the temp directory.

### Example 1
```
PS C:\> Save-ShieldedVMRecoveryKey -DiskNumber 1 -Path 'C:\temp\MyShieldedVMEncryptedRecoveryKey.ebek'
```

Extracts the encrypted recovery key from the second disk (disk number 1) mounted on the system, and saves the recovery key to the temp directory.

## PARAMETERS

### -DiskNumber
Identifier for the mounted disk containing the OS partition of a Windows shielded VM

```yaml
Type: Int32
Parameter Sets: DiskNumberParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Overwrites the encrypted recovery key file located at the specified path

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Location to save the encrypted recovery key

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VHDPath
Location of the VHDX file for a Windows shielded VM to be searched for an encrypted recovery key

```yaml
Type: String
Parameter Sets: VHDParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None


## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Unprotect-ShieldedVMRecoveryKey](Unprotect-ShieldedVMRecoveryKey.md)
