---
external help file: Microsoft.ConfigCI.Commands.dll-Help.xml
Module Name: ConfigCI
online version:
schema: 2.0.0
---

# Set-CIPolicySetting

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### Set
```
Set-CIPolicySetting [-FilePath] <String> -Provider <String> -Key <String> -ValueName <String>
 -ValueType <String> -Value <String> [<CommonParameters>]
```

### Delete
```
Set-CIPolicySetting [-FilePath] <String> -Provider <String> -Key <String> -ValueName <String> [-Delete]
 [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -Delete
{{ Fill Delete Description }}

```yaml
Type: SwitchParameter
Parameter Sets: Delete
Aliases: d

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath
{{ Fill FilePath Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: f

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Key
{{ Fill Key Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: k

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Provider
{{ Fill Provider Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: p

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value
{{ Fill Value Description }}

```yaml
Type: String
Parameter Sets: Set
Aliases: v

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValueName
{{ Fill ValueName Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: vn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValueType
{{ Fill ValueType Description }}

```yaml
Type: String
Parameter Sets: Set
Aliases: vt
Accepted values: Boolean, DWord, Binary, String

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
