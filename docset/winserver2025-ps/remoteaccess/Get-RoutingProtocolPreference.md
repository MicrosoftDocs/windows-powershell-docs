---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RoutingProtocolPreference_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-routingprotocolpreference?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RoutingProtocolPreference
---

# Get-RoutingProtocolPreference

## SYNOPSIS
Displays preferences for routing protocols.

## SYNTAX

```
Get-RoutingProtocolPreference [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-RoutingProtocolPreference** cmdlet displays preferences for routing protocols.
Lower values have higher priority.

Use the Set-RoutingProtocolPreference cmdlet to modify preferences.

## EXAMPLES

### Example 1: Display preferences

```powershell
Get-RoutingProtocolPreference
```

```output
Protocol                                          Priority (Lower value = higher priority)
-----------------------------                     -----------------------------------------------
local                                             1
static                                            3
nondod                                            5
autostatic                                        7
netmgmt                                           10
ebgp                                              15
rip                                               120
ibgp                                              200
```

This command displays the preferences for routing protocols.

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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ProtocolPrefernce

## NOTES

## RELATED LINKS

[Set-RoutingProtocolPreference](./Set-RoutingProtocolPreference.md)

