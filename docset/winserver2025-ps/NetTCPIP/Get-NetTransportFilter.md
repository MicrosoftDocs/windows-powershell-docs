---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetTransportFilter.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nettcpip/get-nettransportfilter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetTransportFilter
---

# Get-NetTransportFilter

## SYNOPSIS
Gets transport filters.

## SYNTAX

```
Get-NetTransportFilter [-SettingName <String[]>] [-Protocol <Protocol[]>] [-LocalPortStart <UInt16[]>]
 [-LocalPortEnd <UInt16[]>] [-RemotePortStart <UInt16[]>] [-RemotePortEnd <UInt16[]>]
 [-DestinationPrefix <String[]>] [-AssociatedTCPSetting <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetTransportFilter** cmdlet gets transport filters.
A transport filter specifies the TCP settings, as a **NetTcpSetting** object, to apply to an IP address prefix or a TCP port range.
Use the cmdlet without parameters to get all transport filters for the computer.

Use the New-NetTransportFilter cmdlet to create transport filters, and use the Remove-NetTransportFilter cmdlet to remove filters.

## EXAMPLES

### Example 1: Get all transport filters
```
PS C:\>Get-NetTransportFilter
```

This command gets all the transport filters on the computer.

### Example 2: Get transport filters that apply specified settings
```
PS C:\>Get-NetTransportFilter -SettingName Internet
```

This command gets transport filters that apply Internet settings.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -AssociatedTCPSetting
Specifies a **NetTCPSetting** object.
The cmdlet gets transport filters associated with the setting that you specify.
To obtain a **NetTCPSetting** object, use the Get-NetTCPSetting cmdlet.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

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

### -DestinationPrefix
Specifies an array of destination prefixes of IP routes.
The cmdlet gets transport filters that have the prefixes that you specify.
A destination prefix consists of an IP address prefix and a prefix length, separated by a slash (/).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalPortEnd
Specifies an array of upper bounds of ranges of local TCP ports.
The cmdlet removes transport filters that have the upper bounds that you specify.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalPortStart
Specifies an array of lower bounds of ranges of local TCP ports.
The cmdlet removes transport filters that have the lower bounds that you specify.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Specifies an array of types of routing protocols.
The cmdlet gets transport filters based on the protocols that you specify.
The acceptable values for this parameter are:

- Bbn
- Bgp
- Dhcp
- Dvmrp
- Egp
- Eigrp
- EsIs
- Ggp
- Hello
- Icmp
- Idpr
- Igrp
- IsIs
- Local
- NetMgmt
- Ospf
- Rip
- Rpl
- Other

```yaml
Type: Protocol[]
Parameter Sets: (All)
Aliases:
Accepted values: TCP, UDP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemotePortEnd
Specifies an array of upper bounds of ranges of remote TCP ports.
The cmdlet removes transport filters that have the upper bounds that you specify.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemotePortStart
Specifies an array of lower bounds of a ranges of remote TCP ports.
The cmdlet removes transport filters that have the lower bounds that you specify.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingName
Specifies an array of setting names.
The cmdlet gets transport filters that have the settings that you specify.
The acceptable values for this parameter are:

- Internet
- Datacenter
- Compat
- Custom

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetTransportFilter
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetUDPSetting](./Get-NetUDPSetting.md)

[New-NetTransportFilter](./New-NetTransportFilter.md)

[Remove-NetTransportFilter](./Remove-NetTransportFilter.md)

[Set-NetTCPSetting](./Set-NetTCPSetting.md)

[Set-NetUDPSetting](./Set-NetUDPSetting.md)

