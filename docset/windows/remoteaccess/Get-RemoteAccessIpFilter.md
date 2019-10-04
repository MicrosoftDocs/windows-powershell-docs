---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_IPFilter_v1.0.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-RemoteAccessIpFilter
ms.reviewer:
ms.assetid: C3BBFF05-2B03-4F5A-96C5-664D3C8C2B53
---

# Get-RemoteAccessIpFilter

## SYNOPSIS
Retrieves IP filters on an interface.

## SYNTAX

```
Get-RemoteAccessIpFilter [-InterfaceAlias] <String> [-Direction] <Direction> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RemoteAccessIpFilter** cmdlet retrieves the existing IP filters on an interface.

## EXAMPLES

### Example 1: Retrieve IP address filters for an interface
```
PS C:\> Get-RemoteAccessIpFilter -InterfaceAlias Interface1 -Direction Outbound


InterfaceAlias   : Interface1
Direction        : outbound
Ipv4FilterAction : allow
Ipv4Filters      : {10.0.0.0/16:10.2.0.0/16:tcp:1234:4321}
Ipv6FilterAction :
Ipv6Filters      :
```

This command retrieves IP filters for traffic on an interface that flows in a specific direction.

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

### -Direction
Specifies the direction of traffic flow, such as inbound, outbound, or both.

```yaml
Type: Direction
Parameter Sets: (All)
Aliases: 
Accepted values: Inbound, OutBound

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -InterfaceAlias
Specifies the alias for an interface.

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

### Microsoft.Management.Infrastructure.CimInstance#InterfaceIpFilter[]

## NOTES

## RELATED LINKS

[Add-RemoteAccessIpFilter](./Add-RemoteAccessIpFilter.md)

[Get-RemoteAccessIpFilter](./Get-RemoteAccessIpFilter.md)

[Set-RemoteAccessIpFilter](./Set-RemoteAccessIpFilter.md)

