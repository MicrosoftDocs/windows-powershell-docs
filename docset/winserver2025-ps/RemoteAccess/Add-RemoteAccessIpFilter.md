---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_IPFilter_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/add-remoteaccessipfilter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-RemoteAccessIpFilter
---

# Add-RemoteAccessIpFilter

## SYNOPSIS
Adds filters for traffic that passes through an interface.

## SYNTAX

```
Add-RemoteAccessIpFilter [-InterfaceAlias] <String> [-Action] <Action> [-List] <String[]>
 [-Direction] <Direction> [-PassThru] [-AddressFamily] <AddressFamily> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-RemoteAccessIpFilter** cmdlet adds IP filters for traffic that passes through an interface.
A filter specifies the types of traffic to allow into or out of a Routing and Remote Access Service (RRAS) server.

You can set packet filters for an interface and configure the filters to do one of the following actions:

- Allow.
Allow all traffic except for packets that are prohibited by filters.
- Deny.
Discard all traffic except for packets that are allowed by filters.

## EXAMPLES

### Example 1: Add a new IP address filter
```
PS C:\> Add-RemoteAccessIpFilter -InterfaceAlias Interface01 -Action Allow -List @("10.0.0.0/16:10.2.0.0/16:TCP:1234:4321") -Direction Outbound -AddressFamily IPv4 -Passthru


InterfaceAlias   : Interface1
Direction        : outbound
Ipv4FilterAction : Allow
Ipv4Filters      : {10.0.0.0/16:10.2.0.0/16:tcp:1234:4321}
Ipv6FilterAction :
Ipv6Filters      :
```

This command adds a new IP address filter for traffic passing through an interface named Interface01.

## PARAMETERS

### -Action
Specifies an action for a filter.

```yaml
Type: Action
Parameter Sets: (All)
Aliases: FilterAction
Accepted values: Allow, Deny

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -AddressFamily
Specifies an IP address family on which to filter.

```yaml
Type: AddressFamily
Parameter Sets: (All)
Aliases:
Accepted values: IPv4, IPv6

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

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

### -Direction
Specifies the direction of traffic flow, such as inbound, outbound, or both.

```yaml
Type: Direction
Parameter Sets: (All)
Aliases:
Accepted values: Inbound, OutBound

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -InterfaceAlias
Specifies an alias for the interface on which to add filters.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -List
Specifies an array of filters to apply.
Use the format SourceIP/Subnet:DestinationIP/Subnet:Protocol:ProtocolData1:ProtocolData2, such as 10.0.0.0/16:10.1.2.3/16:TCP:1234:2345.
If the protocol is TCP or UDP, ProtocolData1 and ProtocolData2 are source and destination port numbers, respectively.
If the protocol is ICMP, ProtocolData1 is Code.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### System.String

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoteAccessIpFilter.Action

### System.String[]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoteAccessIpFilter.Direction

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoteAccessIpFilter.AddressFamily

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance#InterfaceIpFilter

## NOTES

## RELATED LINKS

[Get-RemoteAccessIpFilter](./Get-RemoteAccessIpFilter.md)

[Remove-RemoteAccessIpFilter](./Remove-RemoteAccessIpFilter.md)

[Set-RemoteAccessIpFilter](./Set-RemoteAccessIpFilter.md)

