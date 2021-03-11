---
external help file: PS_BgpRouter_v1.0.cdxml-help.xml
online version: 
schema: 2.0.0
title: Add-BgpRouter
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 82045B7C-A2DB-4ADB-800F-C8FFFE9AAB26
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Add-BgpRouter

## SYNOPSIS
Adds a BGP router.

## SYNTAX

```
Add-BgpRouter -BgpIdentifier <IPAddress> -LocalASN <UInt32> [-IPv6Routing <IPv6RoutingState>]
 [-CompareMEDAcrossASN <Boolean>] [-DefaultGatewayRouting <Boolean>] [-PassThru] [-RoutingDomain <String>]
 [-LocalIPv6Address <IPAddress>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-BgpRouter** cmdlet adds a Border Gateway Protocol (BGP) router.
In a multitenant deployment, the cmdlet adds a BGP router for the routing domain or a tenant.
In a non-multitenant deployment, the cmdlet configures the BGP router for the local computer.
In a multitenant deployment, you must specify the **RoutingDomain** parameter.
In a non-multitenant deployment, do not specify the **RoutingDomain** parameter.

## EXAMPLES

### Example 1: Add a local BGP router
```
PS C:\> Add-BgpRouter -BgpIdentifier "192.168.1.10" -LocalASN 64522 -PassThru



RoutingDomain         :
BgpIdentifier         : 192.168.1.10
LocalASN              : 64522
CompareMEDAcrossASN   : False
DefaultGatewayRouting : False
IPv6Routing           : Disabled
LocalIPv6Address      :
PeerName              :
PolicyName            :
```

This command adds a local BGP router for a tenant.
The command specifies the IP address and ASN of the local router.

### Example 2: Add a local BGP router for a routing domain
```
PS C:\> Add-BgpRouter -RoutingDomain "Rd_001" -BgpIdentifier "10.1.1.10" -LocalASN 64522 -PassThru




RoutingDomain         : Rd_001
BgpIdentifier         : 10.1.1.10
LocalASN              : 64522
CompareMEDAcrossASN   : False
DefaultGatewayRouting : False
IPv6Routing           : Disabled
LocalIPv6Address      :
PeerName              :
PolicyName            :
```

This command adds a local BGP router in a multi-tenant environment for the routing domain named Rd_001.
The command specifies a local BGP router that has the IP address 14.1.1.10, and specifies the BGP router instance that has the local autonomous system number 64522.

## PARAMETERS

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

### -BgpIdentifier
Specifies the Internet IPv4 address of a local BGP router.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -CompareMEDAcrossASN
Indicates whether the BGP router compares Multi-Exit Discriminator (MED) values across different autonomous systems (AS).

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultGatewayRouting
Indicates whether the cmdlet enables routing of the unresolvable routes to the default gateway.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv6Routing
Specifies the state of IPv6 routing for the BGP router.
The acceptable values for this parameter are:

- Enabled
- Disabled

```yaml
Type: IPv6RoutingState
Parameter Sets: (All)
Aliases: 
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalASN
Specifies the local autonomous system number (ASN) for the local router.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalIPv6Address
Specifies the Internet IPv6 address of a local BGP router.
This parameter specifies the global or site-local Internet IPv6 address for the local BGP router.
The BGP router uses this IP address as the next hop value in the IPv6 route advertisements.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -RoutingDomain
Specifies the name, as a string, of a tenant.
The ID of a routing domain is a user-defined alphanumeric string.
A routing domain ID must be unique.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RoutingDomainName

Required: False
Position: Named
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#BgpRouterConfig

## NOTES

## RELATED LINKS

[Get-BgpRouter](./Get-BgpRouter.md)

[Set-BgpRouter](./Set-BgpRouter.md)

[Remove-BgpRouter](./Remove-BgpRouter.md)

