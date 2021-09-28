---
external help file: MSFT_NetEventVFPProvider.cdxml-help.xml
Module Name: NetEventPacketCapture
online version:
schema: 2.0.0
---

# Add-NetEventVFPProvider

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

```
Add-NetEventVFPProvider [-SessionName] <String> [[-Level] <Byte>] [[-UDPPorts] <UInt16[]>]
 [[-MatchAllKeywords] <UInt64>] [[-TCPPorts] <UInt16[]>] [[-MatchAnyKeyword] <UInt64>]
 [[-IPProtocols] <Byte[]>] [[-DestinationIPAddresses] <String[]>] [[-SourceMACAddresses] <String[]>]
 [[-VFPFlowDirection] <UInt32>] [[-VLANIds] <UInt16[]>] [[-SourceIPAddresses] <String[]>]
 [[-TenantIds] <UInt32[]>] [[-GREKeys] <UInt32[]>] [[-DestinationMACAddresses] <String[]>]
 [[-SwitchName] <String>] [[-PortIds] <UInt32[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
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

### -DestinationIPAddresses
{{ Fill DestinationIPAddresses Description }}

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 10
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationMACAddresses
{{ Fill DestinationMACAddresses Description }}

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GREKeys
{{ Fill GREKeys Description }}

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPProtocols
{{ Fill IPProtocols Description }}

```yaml
Type: Byte[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 11
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Level
{{ Fill Level Description }}

```yaml
Type: Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MatchAllKeywords
{{ Fill MatchAllKeywords Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MatchAnyKeyword
{{ Fill MatchAnyKeyword Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PortIds
{{ Fill PortIds Description }}

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 16
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionName
{{ Fill SessionName Description }}

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

### -SourceIPAddresses
{{ Fill SourceIPAddresses Description }}

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceMACAddresses
{{ Fill SourceMACAddresses Description }}

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SwitchName
{{ Fill SwitchName Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 15
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TCPPorts
{{ Fill TCPPorts Description }}

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 12
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TenantIds
{{ Fill TenantIds Description }}

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
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

### -UDPPorts
{{ Fill UDPPorts Description }}

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 13
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VFPFlowDirection
{{ Fill VFPFlowDirection Description }}

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 14
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VLANIds
{{ Fill VLANIds Description }}

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
