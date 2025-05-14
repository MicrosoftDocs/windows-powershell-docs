---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_IPFilter_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/remove-remoteaccessipfilter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-RemoteAccessIpFilter
---

# Remove-RemoteAccessIpFilter

## SYNOPSIS
Removes an IP filter for an interface.

## SYNTAX

```
Remove-RemoteAccessIpFilter [-InterfaceAlias] <String> [-Direction] <Direction> [-List] <String[]> [-PassThru]
 [-Force] [-AddressFamily] <AddressFamily> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-RemoteAccessIpFilter** cmdlet removes an IP filter for an interface.

## EXAMPLES

### Example 1: Remove an IP address filter
```
PS C:\> Remove-RoutingIpFilter -InterfaceAlias Interface01 -Direction Outbound -Force
```

This command removes an IP filter for an interface named Interface01, and traffic that flows in a specific direction.
The command also displays the details of the removed filter.

## PARAMETERS

### -AddressFamily
Specifies the IP address family for which to remove filters.

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -InterfaceAlias
Specifies an alias for the interface for which to remove filters.

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
Specifies an array of filters to remove.
Use the format SourceIP/Subnet:DestinationIP/Subnet:Protocol:ProtocolData1:ProtocolData2 to specify, such as 10.0.0.0/16:10.1.2.3/16:TCP:1234:2345.
If the protocol is TCP or UDP, ProtocolData1 and ProtocolData2 are source and destination port numbers, respectively.
If the protocol is ICMP, ProtocolData1 is Code.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
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

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoteAccessIpFilter.Direction

### System.String[]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoteAccessIpFilter.AddressFamily

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance#InterfaceIpFilter

## NOTES

## RELATED LINKS

[Add-RemoteAccessIpFilter](./Add-RemoteAccessIpFilter.md)

[Get-RemoteAccessIpFilter](./Get-RemoteAccessIpFilter.md)

[Set-RemoteAccessIpFilter](./Set-RemoteAccessIpFilter.md)

