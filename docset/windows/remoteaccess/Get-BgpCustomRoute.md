---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpCustomRoute_v1.0.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-BgpCustomRoute
ms.reviewer:
ms.assetid: 7FC76301-F221-4CD6-8BAD-393F8CFAD2E3
---

# Get-BgpCustomRoute

## SYNOPSIS
Gets custom route information from the BGP router.

## SYNTAX

### RoutingDomain
```
Get-BgpCustomRoute [-RoutingDomain <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### AllRoutingDomains
```
Get-BgpCustomRoute [-AllRoutingDomains] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-BgpCustomRoute** cmdlet gets custom route information from the Border Gateway Protocol (BGP) routing table.
The cmdlet returns the interface and network mask for the custom routes from the BGP routing table.
Custom routes are routes that an administrator configures and adds from a routing interface or network mask to the BGP routing table.
If the BGP router is in a multitenant deployment, you must specify the **RoutingDomain** parameter.
If the BGP router is not in a multitenant deployment, do not specify the **RoutingDomain** parameter,

## EXAMPLES

### Example 1: Get all custom routes from the BGP router
```
PS C:\> Get-BgpCustomRoute




Interface : {Ethernet}
Network   : {172.23.90.0/29}
```

This command gets all the interfaces and network prefixes for all custom routes from the BGP router.

### Example 2: Get custom routes for a routing domain
```
PS C:\> Get-BgpCustomRoute -RoutingDomain "Rd_001"




Interface : {VS1}
Network   :
```

This command gets the interfaces and network prefixes for all custom routes from the BGP router for the routing domain named Rd_001 in a multi-tenant environment.

## PARAMETERS

### -AllRoutingDomains
Use this command to retrieve details about all routing domains.

```yaml
Type: SwitchParameter
Parameter Sets: AllRoutingDomains
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### -RoutingDomain
Specifies  the name, as a string, of a routing domain.
The name of a routing domain is a unique user-defined alphanumeric string.

```yaml
Type: String
Parameter Sets: RoutingDomain
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#BgpCustomNetworkInfo

## NOTES

## RELATED LINKS

[Add-BgpCustomRoute](./Add-BgpCustomRoute.md)

[Remove-BgpCustomRoute](./Remove-BgpCustomRoute.md)

