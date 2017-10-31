---
external help file: Microsoft.Windows.RemoteAttestation.Server.PowerShell.dll-Help.xml
Module Name: HgsAttestation
online version: 
schema: 2.0.0
---

# Add-HgsAttestationDumpPolicy

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### Console (Default)
```
Add-HgsAttestationDumpPolicy [-PublicKeyHash] <String> -Name <String> [-PolicyVersion <PolicyVersion>] [-Stage]
 [-WhatIf] [-Confirm]
```

### File
```
Add-HgsAttestationDumpPolicy [-Path] <String> [-Name <String>] [-PolicyVersion <PolicyVersion>] [-Stage]
 [-WhatIf] [-Confirm]
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

### -Name
{{Fill Name Description}}

```yaml
Type: String
Parameter Sets: Console
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: File
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
{{Fill Path Description}}

```yaml
Type: String
Parameter Sets: File
Aliases: FilePath, PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PolicyVersion
{{Fill PolicyVersion Description}}

```yaml
Type: PolicyVersion
Parameter Sets: (All)
Aliases: 
Accepted values: None, PolicyVersion1503, PolicyVersion1704

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicKeyHash
{{Fill PublicKeyHash Description}}

```yaml
Type: String
Parameter Sets: Console
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Stage
{{Fill Stage Description}}

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

### System.String


## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

