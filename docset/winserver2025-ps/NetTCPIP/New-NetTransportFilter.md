---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetTransportFilter.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nettcpip/new-nettransportfilter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetTransportFilter
---

# New-NetTransportFilter

## SYNOPSIS
Creates a transport filter.

## SYNTAX

```
New-NetTransportFilter -SettingName <String> [-Protocol <Protocol>] [-LocalPortStart <UInt16>]
 [-LocalPortEnd <UInt16>] [-RemotePortStart <UInt16>] [-RemotePortEnd <UInt16>] [-DestinationPrefix <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetTransportFilter** cmdlet creates a transport filter.
A transport filter specifies the TCP settings, as a **NetTcpSetting** object, to apply to an IP address prefix or a TCP port range.
Specify the setting to apply by name.
You can use the Set-NetTCPSetting cmdlet to modify a setting.

## EXAMPLES

### Example 1: Create a transport filter
```
PS C:\>New-NetTransportFilter -SettingName Datacenter -DestinationPrefix 192.168.0.0/16
```

This command creates a transport filter for the 192.168.0.0/16 network.
The data center TCP settings applies to all TCP connections between the computer and other computers in this network.

### Example 2: Create a transport filter for an app
```
PS C:\>Get-NetTransportFilter -SettingName Compat -LocalPortStart 5000 -LocalPortEnd 5000 -RemotePortStart 6000 -RemotePortEnd 6000
```

This command creates a transport filter for a compatibility setting.
The command specifies port ranges for both local and remote computers.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationPrefix
Specifies a destination prefix of an IP route.
The cmdlet associates the transport filter that to the prefix that you specify.
A destination prefix consists of an IP address prefix and a prefix length, separated by a slash (/).

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalPortEnd
Specifies the upper bound of a range of local TCP ports.
The cmdlet assigns the upper bound that you specify to the transport filter.
If you do not specify this parameter, the cmdlet uses the lower range value of 1025.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalPortStart
Specifies the lower bound of a range of local TCP ports.
The cmdlet assigns the lower bound that you specify to the transport filter.
If you do not specify this parameter, the cmdlet uses the lower range value of 65535.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Specifies the type of routing protocol.
The cmdlet assigns the protocol that you specify to the routing filter.
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
Type: Protocol
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
Specifies the upper bound of a range of remote TCP ports.
The cmdlet assigns the upper bound that you specify to the transport filter.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemotePortStart
Specifies the lower bound of a range of remote TCP ports.
The cmdlet assigns the lower bound that you specify to the transport filter.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingName
Specifies a setting name.
The cmdlet associates the setting that you specify to the transport filter.
The acceptable values for this parameter are:

- Internet
- Datacenter
- Compat
- Custom

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
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

[Get-NetTransportFilter](./Get-NetTransportFilter.md)

[Remove-NetTransportFilter](./Remove-NetTransportFilter.md)

[Set-NetTCPSetting](./Set-NetTCPSetting.md)

