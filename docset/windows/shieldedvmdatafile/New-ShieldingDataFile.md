---
external help file: Microsoft.Windows.HardenedFabric.Cmdlets.dll-Help.xml
Module Name: ShieldedVMDataFile
online version: 
schema: 2.0.0
---

# New-ShieldingDataFile

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### ShieldedTemplateParameterSet
```
New-ShieldingDataFile [-ShieldingDataFilePath] <String> [-Owner] <Guardian>
 [-VolumeIDQualifier] <VolumeIDQualifier[]> [-AnswerFile] <NamedFileContent>
 [[-OtherFile] <NamedFileContent[]>] [[-Guardian] <Guardian[]>] [-Policy <FabricPolicyValue>] [-WhatIf]
 [-Confirm]
```

### ExistingVMParameterSet
```
New-ShieldingDataFile [-ShieldingDataFilePath] <String> [-Owner] <Guardian> [[-OtherFile] <NamedFileContent[]>]
 [[-Guardian] <Guardian[]>] [-Policy <FabricPolicyValue>] [-WhatIf] [-Confirm]
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

### -AnswerFile
{{Fill AnswerFile Description}}

```yaml
Type: NamedFileContent
Parameter Sets: ShieldedTemplateParameterSet
Aliases: WindowsUnattendFile

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Guardian
{{Fill Guardian Description}}

```yaml
Type: Guardian[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OtherFile
{{Fill OtherFile Description}}

```yaml
Type: NamedFileContent[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Owner
{{Fill Owner Description}}

```yaml
Type: Guardian
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Policy
{{Fill Policy Description}}

```yaml
Type: FabricPolicyValue
Parameter Sets: (All)
Aliases: 
Accepted values: Shielded, EncryptionSupported

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ShieldingDataFilePath
{{Fill ShieldingDataFilePath Description}}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeIDQualifier
{{Fill VolumeIDQualifier Description}}

```yaml
Type: VolumeIDQualifier[]
Parameter Sets: ShieldedTemplateParameterSet
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Windows.HardenedFabric.Cmdlets.Common.Guardian
Microsoft.Windows.HardenedFabric.Cmdlets.Common.VolumeIDQualifier[]
Microsoft.Windows.HardenedFabric.Cmdlets.Common.NamedFileContent
Microsoft.Windows.HardenedFabric.Cmdlets.Common.NamedFileContent[]
Microsoft.Windows.HardenedFabric.Cmdlets.Common.Guardian[]
Microsoft.Windows.HardenedFabric.Cmdlets.Common.FabricPolicyValue


## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

