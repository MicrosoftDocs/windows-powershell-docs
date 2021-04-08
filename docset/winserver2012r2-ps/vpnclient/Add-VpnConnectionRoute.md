---
author: Kateyanne
description: 
external help file: PS_VpnConnectionRoute_v1.0.cdxml-help.xml
manager: jasgro
Module Name: VpnClient
ms.author: v-kaunu
ms.date: 10/29/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/vpnclient/add-vpnconnectionroute?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VpnConnectionRoute
---

# Add-VpnConnectionRoute

## SYNOPSIS
Adds a route to a VPN connection.

## SYNTAX

```
Add-VpnConnectionRoute [-ConnectionName] <String> [-DestinationPrefix] <String> [[-RouteMetric] <UInt32>]
 [-PassThru] [-AllUserConnection] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-VpnConnectionRoute** cmdlet adds an IPv4 or IPv6 route to a specified VPN connection.

## EXAMPLES

### Example 1: Add a VPN connection route for an IPv4 address
```
PS C:\> Add-VpnConnectionRoute -ConnectionName "Contoso" -DestinationPrefix 176.16.0.0/16 -PassThru
DestinationPrefix : 176.16.0.0/16

InterfaceIndex    :

InterfaceAlias    : Contoso

AddressFamily     : IPv4

NextHop           : 0.0.0.0

Publish           : 0

RouteMetric       : 1

PolicyStore       :
```

This command uses the **Add-VpnConnectionRoute** cmdlet to add a connection route for the connection named Contoso.
The command specifies an IPv4 address for the **DestinationPrefix** parameter.

### Example 2: Add a VPN connection for an IPv6 address
```
PS C:\> Add-VpnConnectionRoute -ConnectionName "Contoso" -DestinationPrefix 2001:4898:7020:3020::/64 -RouteMetric 23 -PassThru
DestinationPrefix : 2001:4898:7020:3020::/64

InterfaceIndex    :

InterfaceAlias    : Contoso

AddressFamily     : IPv6

NextHop           : ::

Publish           : 0

RouteMetric       : 23

PolicyStore       :
```

This command uses the **Add-VpnConnectionRoute** cmdlet to add a connection route for the connection named Contoso.
The command specifies an IPv6 address for the **DestinationPrefix** parameter.

## PARAMETERS

### -AllUserConnection
Indicates that the VPN connection being modified is in the global phone book.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -ConnectionName
Specifies the name of a VPN connection profile.
To view existing VPN connection profiles, use the Get-VpnConnection cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationPrefix
Specifies the destination prefix of the route to add.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.
If you specify this parameter, the cmdlet returns the **MSFT_NetRoute** object.

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

### -RouteMetric
Specifies the metric of the route being added to the VPN connection.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetRoute

## NOTES

## RELATED LINKS

[Remove-VpnConnectionRoute](./Remove-VpnConnectionRoute.md)

