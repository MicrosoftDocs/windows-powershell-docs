---
external help file: PS_BgpRoute_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-bgprouteinformation?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-BgpRouteInformation
---

# Get-BgpRouteInformation

## SYNOPSIS
Gets route information for network prefixes from the BGP router.

## SYNTAX

```
Get-BgpRouteInformation [-Network <String[]>] [-RoutingDomain <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-BgpRouteInformation** cmdlet gets the route information for network prefixes from the Border Gateway Protocol (BGP) routing table.
The cmdlet gets information about routes that the BGP router learned through the exchange of information with other routers.
If you do not specify the **Network** parameter, the cmdlet gets route information for all network prefixes from the BGP routing table.

## EXAMPLES

### Example 1: Get learned routes from a BGP router
```
PS C:\> Get-BgpRouteInformation



DestinationNetwork      NextHop                 LearnedFromPeer         LocalPref               MED
------------------      -------                 ------                  ---------               ---
172.23.90.0/28          172.23.90.9             BlueTenantSite1
172.23.90.15/32         172.23.90.9             INCOMPLETE
```

This command gets information for all learned routes from the local BGP router.

### Example 2: Get BGP learned routes for a routing domain
```
PS C:\> Get-BgpRouteInformation -RoutingDomain "Rd002"



DestinationNetwork      NextHop                 LearnedFromPeer         LocalPref               MED
------------------      -------                 ------                  ---------               ---
192.0.2.0/24            172.23.90.5             RedTenantSite1
198.51.100.0/24         172.23.90.5             RedTenantSite1
203.0.113.0/24          172.23.90.5             RedTenantSite1
206.73.118.0/24         172.23.90.5             RedTenantSite1
```

This command gets information for the learned routes from the router for the routing domain named Rd002.

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

### -Network
Specifies an array of network prefixes, in Classless InterDomain Routing (CIDR) notation.

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
Specifies the name, as a string, of a routing domain.
The name of a routing domain is a unique user-defined alphanumeric string.

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

### Microsoft.Management.Infrastructure.CimInstance#BgpRouteInfo[]

## NOTES

## RELATED LINKS

[Get-BgpRouter](./Get-BgpRouter.md)

[Get-BgpCustomRoute](./Get-BgpCustomRoute.md)

