---
external help file: MSFT_NetEventVFPProvider.cdxml-help.xml
Module Name: NetEventPacketCapture
online version:
schema: 2.0.0
---

# Set-NetEventVFPProvider

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### BySessionName (Default)
```
Set-NetEventVFPProvider [[-SessionName] <String[]>] [[-Level] <Byte>] [[-MatchAnyKeyword] <UInt64>]
 [[-MatchAllKeyword] <UInt64>] [[-VFPFlowDirection] <VFPFlowDirection>] [[-DestinationMACAddresses] <String[]>]
 [[-TCPPorts] <UInt16[]>] [[-UDPPorts] <UInt16[]>] [[-SourceMACAddresses] <String[]>] [[-VLANIds] <UInt16[]>]
 [[-GREKeys] <UInt32[]>] [[-TenantIds] <UInt32[]>] [[-SourceIPAddresses] <String[]>]
 [[-DestinationIPAddresses] <String[]>] [[-IPProtocols] <Byte[]>] [[-SwitchName] <String>]
 [[-PortIds] <UInt32[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### BySessionOfTheProvider
```
Set-NetEventVFPProvider [-AssociatedEventSession <CimInstance>] [[-Level] <Byte>] [[-MatchAnyKeyword] <UInt64>]
 [[-MatchAllKeyword] <UInt64>] [[-VFPFlowDirection] <VFPFlowDirection>] [[-DestinationMACAddresses] <String[]>]
 [[-TCPPorts] <UInt16[]>] [[-UDPPorts] <UInt16[]>] [[-SourceMACAddresses] <String[]>] [[-VLANIds] <UInt16[]>]
 [[-GREKeys] <UInt32[]>] [[-TenantIds] <UInt32[]>] [[-SourceIPAddresses] <String[]>]
 [[-DestinationIPAddresses] <String[]>] [[-IPProtocols] <Byte[]>] [[-SwitchName] <String>]
 [[-PortIds] <UInt32[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetEventVFPProvider -InputObject <CimInstance[]> [[-Level] <Byte>] [[-MatchAnyKeyword] <UInt64>]
 [[-MatchAllKeyword] <UInt64>] [[-VFPFlowDirection] <VFPFlowDirection>] [[-DestinationMACAddresses] <String[]>]
 [[-TCPPorts] <UInt16[]>] [[-UDPPorts] <UInt16[]>] [[-SourceMACAddresses] <String[]>] [[-VLANIds] <UInt16[]>]
 [[-GREKeys] <UInt32[]>] [[-TenantIds] <UInt32[]>] [[-SourceIPAddresses] <String[]>]
 [[-DestinationIPAddresses] <String[]>] [[-IPProtocols] <Byte[]>] [[-SwitchName] <String>]
 [[-PortIds] <UInt32[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
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

### -DestinationIPAddresses
{{ Fill DestinationIPAddresses Description }}

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3012
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
Position: 3006
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
Position: 3010
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
{{ Fill InputObject Description }}

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IPProtocols
{{ Fill IPProtocols Description }}

```yaml
Type: Byte[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3013
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
Position: 3003
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MatchAllKeyword
{{ Fill MatchAllKeyword Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: 3005
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
Position: 3004
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
{{ Fill PassThru Description }}

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

### -PortIds
{{ Fill PortIds Description }}

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3018
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

### -SourceIPAddresses
{{ Fill SourceIPAddresses Description }}

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3011
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
Position: 3007
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
Position: 3017
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
Position: 3014
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
Position: 3009
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
Position: 3015
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VFPFlowDirection
{{ Fill VFPFlowDirection Description }}

```yaml
Type: VFPFlowDirection
Parameter Sets: (All)
Aliases:
Accepted values: Inbound, Outbound, InboundAndOutbound

Required: False
Position: 3016
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
Position: 3008
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

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#root/StandardCimv2/MSFT_NetEventVFPProvider

## NOTES

## RELATED LINKS
