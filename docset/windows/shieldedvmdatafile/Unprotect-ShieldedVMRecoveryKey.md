---
external help file: Microsoft.Windows.HardenedFabric.Cmdlets.dll-Help.xml
Module Name: ShieldedVMDataFile
online version: 
schema: 2.0.0
---

# Unprotect-ShieldedVMRecoveryKey

## SYNOPSIS
{{Fill in the Synopsis}}

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
{{Fill in the Description}}

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -DecryptedBitLockerKeyPath
{{Fill DecryptedBitLockerKeyPath Description}}

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
{{Fill EncryptedBitLockerKeyPath Description}}

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
{{Fill Recurse Description}}

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
{{Fill ShieldingDataFilePath Description}}

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
{{Fill ShieldingDataFileSearchPath Description}}

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

### System.Object

## NOTES

## RELATED LINKS

