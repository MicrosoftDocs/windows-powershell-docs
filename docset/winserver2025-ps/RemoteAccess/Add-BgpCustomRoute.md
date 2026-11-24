---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpCustomRoute_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/add-bgpcustomroute?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-BgpCustomRoute
---

# Add-BgpCustomRoute

## SYNOPSIS
Adds custom routes to the BGP routing table.

## SYNTAX

```
Add-BgpCustomRoute [-PassThru] [-RoutingDomain <String>] [-Interface <String[]>] [-Network <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Add-BgpCustomRoute** cmdlet adds custom routes from router interfaces and network prefixes to the Border Gateway Protocol (BGP) routing table.
The cmdlet returns information about any errors that occur when you add the routes to the BGP routing table.

Use the **Interface** parameter to specify the router interfaces.
Use the **Network** parameter to specify the network prefixes.
Use the **RoutingDomain** parameter to specify the routing domain or tenant of the BGP router in a multitenant deployment.

## EXAMPLES

### Example 1: Add an interface to a BGP router
```
PS C:\> Add-BgpCustomRoute -Interface "Ethernet" -PassThru




Interface : {Ethernet}
Network   :
```

This command adds the interface named Ethernet to the local BGP router.
The cmdlet adds all the unicast IP addresses of the interface to the BGP router.

### Example 2: Add a network prefix to a BGP router
```
PS C:\> Add-BgpCustomRoute -Network "172.23.90.0/29" -PassThru




Interface : {Ethernet}
Network   : {172.23.90.0/29}
```

This command adds the routing information from the network prefix 172.23.90.0/29 to the local BGP router.

### Example 3: Add an interface and a network prefix to a BGP router for a routing domain
```
PS C:\> Add-BgpCustomRoute -Interface "VS1" -Network "172.23.90/29" -RoutingDomain "Rd_001" -PassThru




Interface : {Ethernet}
Network   : {172.23.90.0/29}
```

This command adds the routing information from the interface named VS1 and the network prefix 172.23.90.0 to the BGP router for the routing domain in a multitenant environment named Rd_001.
The command includes the **PassThru** parameter, so the command sends a **BgpCustomNetworkInfo** object to the console.

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

### -Interface
Specifies an array of names of router interfaces.
The cmdlet adds the static routes from these interfaces to the BGP routing table.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Network
Specifies an array of network prefixes, in Classless InterDomain Routing (CIDR) notation.
The cmdlet adds the routing information for the network prefixes to the BGP routing table.

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
Specifies the name, as a string, of the routing domain.
The cmdlet adds the custom routes to the BGP routing table for this routing domain.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#BgpCustomNetworkInfo

## NOTES

## RELATED LINKS

[Get-BgpCustomRoute](./Get-BgpCustomRoute.md)

[Remove-BgpCustomRoute](./Remove-BgpCustomRoute.md)

