---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpRouter_v1.0.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-BgpRouter
ms.reviewer:
ms.assetid: 63AC9E9F-C0A5-438B-B763-83D384EBA85A
---

# Get-BgpRouter

## SYNOPSIS
Gets configuration information for BGP routers.

## SYNTAX

```
Get-BgpRouter [-RoutingDomain <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-BgpRouter** cmdlet gets router configuration information for Border Gateway Protocol (BGP) routers.
In a multitenant deployment, the cmdlet adds a BGP router for the routing domain or a tenant.
In a non-multitenant deployment, the cmdlet configures the BGP router for the local computer.
In a multitenant deployment, you must specify the **RoutingDomain** parameter.
In a non-multitenant deployment, do not specify the **RoutingDomain** parameter.

## EXAMPLES

### Example 1: Get configuration information of a BGP router
```
PS C:\> Get-BgpRouter



RoutingDomain         :
BgpIdentifier         : 192.168.1.10
LocalASN              : 64513
CompareMEDAcrossASN   : False
DefaultGatewayRouting : False
IPv6Routing           : Disabled
LocalIPv6Address      :
PeerName              :
PolicyName            :
```

This command gets the configuration information of the local BGP router.

### Example 2: Get configuration information of a router for a routing domain
```
PS C:\> Get-BgpRouter -RoutingDomain "Rd_001"




RoutingDomain         : Rd_001
BgpIdentifier         : 172.22.226.39
LocalASN              : 64522
CompareMEDAcrossASN   : False
DefaultGatewayRouting : False
IPv6Routing           : Disabled
LocalIPv6Address      :
PeerName              : {Tenant01}
PolicyName            :
```

This command gets the configuration information of the BGP router for the routing domain that has the ID Rd_001.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -RoutingDomain
Specifies an name, as a string, of a routing domain.
The name of a routing domain is a unique user-defined alphanumeric string.

```yaml
Type: String[]
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#BgpRouterConfig[]

## NOTES

## RELATED LINKS

[Add-BgpRouter](./Add-BgpRouter.md)

[Set-BgpRouter](./Set-BgpRouter.md)

[Remove-BgpRouter](./Remove-BgpRouter.md)

