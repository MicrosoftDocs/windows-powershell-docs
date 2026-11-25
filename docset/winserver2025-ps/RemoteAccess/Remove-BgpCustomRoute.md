---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpCustomRoute_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/remove-bgpcustomroute?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-BgpCustomRoute
---

# Remove-BgpCustomRoute

## SYNOPSIS
Removes custom routes from the BGP router.

## SYNTAX

```
Remove-BgpCustomRoute [-Network <String[]>] [-Interface <String[]>] [-Force] [-RoutingDomain <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-BgpCustomRoute** cmdlet removes Classless InterDomain Routing (CIDR) prefixes or interfaces for custom routes from the Border Gateway Protocol (BGP) routing table.
When you remove a custom route, the BGP router can no longer use the information from the CIDR network or interface to distribute routing information between autonomous systems (AS).
In addition, the BGP router sends route withdrawal messages to peers to remove the previously advertised custom routes that you remove.

You must specify at least one of the **Interface** or **Network** parameters.

## EXAMPLES

### Example 1: Remove a network prefix
```
PS C:\> Remove-BgpCustomRoute -Network "172.23.90.0/29"



Confirm
Removing specified custom networks from BGP router. Do you want to continue?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):Y
```

This command removes the network prefix of a custom network from the BGP routing table.

### Example 2: Remove the interface for a routing domain
```
PS C:\> Remove-BgpCustomRoute -Interface "VS01" -RoutingDomain Rd_002



Confirm
Removing specified custom networks from BGP router of Routing Domain Rd_002. Do you want to continue?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):Y
```

This command removes the router interface named VS01 from the BGP routing table for the routing domain named Rd_002.

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

### -Interface
Specifies an array of names of router interfaces.
The cmdlet removes the static routes for these interfaces from the BGP routing table.

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
For IPv4 networks, you must specify the network prefix and its network mask.
The cmdlet removes the routing information for the network prefixes from the BGP routing table.

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

### System.String[]

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-BgpCustomRoute](./Add-BgpCustomRoute.md)

[Add-BgpCustomRoute](./Add-BgpCustomRoute.md)

