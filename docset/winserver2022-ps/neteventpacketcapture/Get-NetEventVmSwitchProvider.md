---
external help file: MSFT_NetEventVmSwitchProvider.cdxml-help.xml
Module Name: NetEventPacketCapture
online version:
schema: 2.0.0
---

# Get-NetEventVmSwitchProvider

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### BySessionName (Default)
```
Get-NetEventVmSwitchProvider [[-SessionName] <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### BySessionOfTheProvider
```
Get-NetEventVmSwitchProvider [-AssociatedEventSession <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
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

### -AsJob
{{ Fill AsJob Description }}

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

### -AssociatedEventSession
{{ Fill AssociatedEventSession Description }}

```yaml
Type: CimInstance
Parameter Sets: BySessionOfTheProvider
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CimSession
{{ Fill CimSession Description }}

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionName
{{ Fill SessionName Description }}

```yaml
Type: String[]
Parameter Sets: BySessionName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
{{ Fill ThrottleLimit Description }}

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#root/StandardCimv2/MSFT_NetEventVmSwitchProvider

## NOTES

## RELATED LINKS
