---
external help file: Microsoft.Windows.HardenedFabric.Cmdlets.dll-Help.xml
Module Name: ShieldedVMDataFile
online version: https://learn.microsoft.com/powershell/module/shieldedvmdatafile/unprotect-shieldedvmrecoverykey?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Unprotect-ShieldedVMRecoveryKey
---

# Unprotect-ShieldedVMRecoveryKey

## SYNOPSIS
Decrypts an encrypted recovery key for a Windows shielded VM obtained from the [Save-ShieldedVMRecoveryKey](Save-ShieldedVMRecoveryKey.md) cmdlet.

## SYNTAX

### EBEKFileParameterSet (Default)
```
Unprotect-ShieldedVMRecoveryKey -ShieldingDataFilePath <String> -EncryptedBitLockerKeyPath <String>
 -DecryptedBitLockerKeyPath <String> [-WhatIf] [-Confirm]
```

### EBEKFileSearchParameterSet
```
Unprotect-ShieldedVMRecoveryKey -ShieldingDataFileSearchPath <String[]> [-Recurse]
 -EncryptedBitLockerKeyPath <String> -DecryptedBitLockerKeyPath <String> [-WhatIf] [-Confirm]
```

## DESCRIPTION
The *Unprotect-ShieldedVMRecoveryKey* cmdlet decrypts an encrypted BitLocker recovery key file obtained from a Windows shielded VM.
To run the cmdlet, you must have the shielding data file that was used to deploy the shielded VM and have the private key for the owner guardian installed on your computer.

The resulting recovery key can be provided to `manage-bde.exe`, `Unlock-BitLocker`, or the BitLocker Recovery pre-boot environment to access the contents of your shielded VM OS volume.

## EXAMPLES

### Example 1
```
PS C:\> Unprotect-ShieldedVMRecoveryKey -ShieldingDataFilePath 'C:\temp\ShieldingDataFile.pdk' -EncryptedBitLockerKeyPath 'C:\temp\MyShieldedVMEncryptedRecoveryKey.ebek' -DecryptedBitLockerKeyPath 'C:\temp\DecryptedRecoveryKey.bek'
```

Decrypts the provided encrypted BitLocker recovery key using the shielding data file and owner guardian private keys, and saves it to the temp directory.

### Example 2
```
PS C:\> Unprotect-ShieldedVMRecoveryKey -ShieldingDataSearchPath 'C:\temp\AllShieldingDataFiles\' -Recurse -EncryptedBitLockerKeyPath 'C:\temp\MyShieldedVMEncryptedRecoveryKey.ebek' -DecryptedBitLockerKeyPath 'C:\temp\DecryptedRecoveryKey.bek'
```

Searches the 'AllShieldingDataFiles' directory and all subdirectories for shielding data files that can be used to decrypt the provided encrypted BitLocker recovery key.
If a suitable shielding data file is found and the private key for its owner guardian is available on the local computer, the decrypted BitLocker encryption key will be saved to the temp directory.

## PARAMETERS

### -DecryptedBitLockerKeyPath
Location to save the decrypted BitLocker encryption key (.bek)

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

### -EncryptedBitLockerKeyPath
Location of the encrypted BitLocker encryption key

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

### -Recurse
Specifies the cmdlet should search subdirectories of the shielding data file search path for compatible PDK files.

```yaml
Type: SwitchParameter
Parameter Sets: EBEKFileSearchParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShieldingDataFilePath
Location of the shielding data file (.pdk) used to deploy the shielded VM.

```yaml
Type: String
Parameter Sets: EBEKFileParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShieldingDataFileSearchPath
Location of one or more directories to search for a shielding data file that can be used to decrypt the provided encrypted BitLocker encryption key.

```yaml
Type: String[]
Parameter Sets: EBEKFileSearchParameterSet
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

[Save-ShieldedVMRecoveryKey](Save-ShieldedVMRecoveryKey.md)
