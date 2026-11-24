---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpRouteAggregate_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-bgprouteaggregate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-BgpRouteAggregate
---

# Get-BgpRouteAggregate

## SYNOPSIS
Gets all the aggregate BGP routes configured by the administrator.

## SYNTAX

```
Get-BgpRouteAggregate [-RoutingDomain <String>] [-Prefix <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-BgpRouteAggregate** cmdlet retrieves all the aggregate Border Gateway Protocol (BGP) routes configured by the administrator.

## EXAMPLES

### Example 1: Get a custom aggregate route and its aggregate policies
```
PS C:\>Get-BgpRouteAggregate -Prefix "172.168.0.0/16", "10.10.10.0/24"
```

This command gets a custom aggregate route and its aggregate policies for aggregate IP addresses 172.168.0.0/16 and 10.10.10.0/24.

### Example 2: Retrieve all aggregate routes and their aggregate policies
```
PS C:\>Get-BgpRouteAggregate
```

This command gets all aggregate routes and their aggregate policies.

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

### -Prefix
Specifies a string array of the aggregate IP addresses (classless IP address prefixes and their prefix lengths) whose properties are to be retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: AggregatePrefix

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

### System.String

### System.String[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance#BgpRouteAggregateInfo

## NOTES

## RELATED LINKS

[Add-BgpRouteAggregate](./Add-BgpRouteAggregate.md)

[Remove-BgpRouteAggregate](./Remove-BgpRouteAggregate.md)

[Set-BgpRouteAggregate](./Set-BgpRouteAggregate.md)

[Remote Access Cmdlets](./remoteaccess.md)

