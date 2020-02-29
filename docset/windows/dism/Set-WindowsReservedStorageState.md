---
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: dism
online version: https://go.microsoft.com/fwlink/?LinkId=289367
schema: 2.0.0
---

# Set-WindowsReservedStorageState

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

```
Set-WindowsReservedStorageState -State <ReservedStorageState> [-LogPath <String>] [-ScratchDirectory <String>]
 [-LogLevel <LogLevel>] [<CommonParameters>]
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

### -LogLevel
{{ Fill LogLevel Description }}

```yaml
Type: LogLevel
Parameter Sets: (All)
Aliases: LL
Accepted values: Errors, Warnings, WarningsInfo

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogPath
{{ Fill LogPath Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: LP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScratchDirectory
{{ Fill ScratchDirectory Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State
{{ Fill State Description }}

```yaml
Type: ReservedStorageState
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Dism.Commands.ReservedStorageState

### System.String

### Microsoft.Dism.Commands.LogLevel

## OUTPUTS

### Microsoft.Dism.Commands.ReservedStorageStateObject

## NOTES

## RELATED LINKS
