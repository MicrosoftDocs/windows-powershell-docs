---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpRoute_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-bgprouteinformation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-BgpRouteInformation
---

# Get-BgpRouteInformation

## SYNOPSIS
Retrieves BGP route information for one or more network prefixes from the BGP routing table.

## SYNTAX

```
Get-BgpRouteInformation [-Network <String[]>] [-RoutingDomain <String>] [-Type <RouteType>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-BgpRouteInformation** cmdlet retrieves Border Gateway Protocol (BGP) route information for one or more network prefixes.
This cmdlet returns error information if errors occur while retrieving the BGP route information.

## EXAMPLES

### Example 1:Get all BGP learned routes
```
PS C:\>Get-BgpRouteInformation
DestinationNetwork      NextHop                 Origin                  LocalPref               MED
------------------      -------                 ------                  ---------               ---
172.23.90.0/28          172.23.90.9             INCOMPLETE
172.23.90.15/32         172.23.90.9             INCOMPLETE
```

This command gets the BGP learned routes

### Example 2: Get the BGP learned routes for a specified routing domain
```
PS C:\>Get-BgpRouteInformation -RoutingDomain Rd_002
DestinationNetwork      NextHop                 Origin                  LocalPref               MED
------------------      -------                 ------                  ---------               ---
100.0.0.0/24            172.23.90.5             INCOMPLETE
100.0.0.5/32            172.23.90.5             INCOMPLETE
100.0.0.6/32            172.23.90.5             INCOMPLETE
100.0.0.255/32          172.23.90.5             INCOMPLETE
```

This command gets the BGP learned routes for the specified routing domain in Multi-Tenant Environment.

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

### -Network
Specifies a string array of CIDR IPv4 and IPv6 network prefixes along with network masks for which the BGP routing information is to be retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: DestinationNetwork

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoutingDomain
Specifies the user-defined unique alphanumeric identifier for the routing domain.

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
Specifies the maximum number of concurrent connections that can be established to run this command.
If you omit this parameter or enter a value of 0, the default value, 32, is used.

The throttle limit applies only to the current command, not to the session or to the computer.

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

### -Type
Specifies the type of routes for which the information needs to be retrieved or listed.

```yaml
Type: RouteType
Parameter Sets: (All)
Aliases:
Accepted values: All, Best, Damped, Suppressed

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### System.String

### System.Nullable`1[[Microsoft.PowerShell.Cmdletization.GeneratedTypes.Bgp.RouteType, Microsoft.PowerShell.Cmdletization.GeneratedTypes, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance#BgpRouteInfo

## NOTES

## RELATED LINKS

[Remote Access Cmdlets](./remoteaccess.md)

