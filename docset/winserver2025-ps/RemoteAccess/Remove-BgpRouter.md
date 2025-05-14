---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpRouter_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/remove-bgprouter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-BgpRouter
---

# Remove-BgpRouter

## SYNOPSIS
Removes a BGP router.

## SYNTAX

```
Remove-BgpRouter [-RoutingDomain <String[]>] [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-BgpRouter** cmdlet removes BGP router routers.
In a multitenant deployment, the cmdlet removes a BGP router for the routing domain or a tenant.
In a non-multitenant deployment, the cmdlet removes the BGP router for the local computer.
When you remove a BGP router, the BGP router can no longer read and distribute routing information between autonomous systems (AS).
In addition, the other routers that added the router as a peer delete all the information learned from the router and recalculate their routes accordingly.

## EXAMPLES

### Example 1: Remove BGP routing
```
PS C:\> Remove-BgpRouter


Confirm
Are you sure you want to remove the BGP router and stop any active BGP peering sessions?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```

This command removes BGP routing from the local router.
The command prompts the user for confirmation before removing the BGP Router.

### Example 2: Remove BGP routing without confirmation
```
PS C:\> Remove-BgpRouter -Force
```

This command removes BGP routing from the local router.
The command does not prompt the user for confirmation before removing BGP routing.

### Example 3: Remove BGP routers for routing domains
```
PS C:\> Remove-BgpRouter -RoutingDomain "Rd_001","Rd_002"



Confirm
Are you sure you want to remove the BGP router for routing domain Rd_001 and stop any active BGP peering sessions?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):

Confirm
Are you sure you want to remove the BGP router for routing domain Rd_002 and stop any active BGP peering sessions?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

This command removes the BGP routers from the routing domains named Rd_001 and Rd_002.
The command prompts the user for confirmation before removing the BGP routers.

### Example 4: Remove BGP routers for a routing domain without confirmation
```
PS C:\> Remove-BgpRouter -RoutingDomain "Rd_002" -Force
```

This command removes the BGP routers from the routing domain named Rd_002.
The command does not prompt the user for confirmation before removing the BGP routers.

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

### -RoutingDomain
Specifies an ID, as a string, for a routing domain.
The ID of a routing domain is a unique user-defined alphanumeric string.

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

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-BgpRouter](./Get-BgpRouter.md)

[Add-BgpRouter](./Add-BgpRouter.md)

[Set-BgpRouter](./Set-BgpRouter.md)

