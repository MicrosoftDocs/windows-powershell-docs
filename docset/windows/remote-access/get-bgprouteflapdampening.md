---
author: brianlic
description: 
external help file: PS_BgpRouteFlapDampening_v1.0.cdxml-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-BgpRouteFlapDampening
ms.assetid: 94833F9A-9A01-4816-851D-71D152B290DE
---

# Get-BgpRouteFlapDampening

## SYNOPSIS
Retrieves the configuration of a BGP route dampening engine.

## SYNTAX

```
Get-BgpRouteFlapDampening [-RoutingDomain <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-BgpRouteFlapDampening** cmdlet retrieves the configuration of a Border Gateway Protocol (BGP) route dampening engine.

## EXAMPLES

### Example 1: Get BGP route flap dampening configuration
```
PS C:\>Get-BgpRouteFlapDampening -RoutingDomain "Contoso"
```

This command gets BGP route flap dampening configuration from the routing domain named Contoso.

## PARAMETERS

### -AsJob
{{Fill AsJob Description}}

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#BgpRouteFlapDampeningConfig

## NOTES

## RELATED LINKS

[Clear-BgpRouteFlapDampening](./Clear-BgpRouteFlapDampening.md)

[Disable-BgpRouteFlapDampening](./Disable-BgpRouteFlapDampening.md)

[Enable-BgpRouteFlapDampening](./Enable-BgpRouteFlapDampening.md)

[Set-BgpRouteFlapDampening](./Set-BgpRouteFlapDampening.md)

[Remote Access Cmdlets](./RemoteAccess.md)

