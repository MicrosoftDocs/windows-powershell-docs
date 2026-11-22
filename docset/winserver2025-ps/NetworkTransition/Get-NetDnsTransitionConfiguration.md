---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetDnsTransitionConfiguration.cdxml-help.xml
Module Name: NetworkTransition
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networktransition/get-netdnstransitionconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetDnsTransitionConfiguration
---

# Get-NetDnsTransitionConfiguration

## SYNOPSIS
Retrieves the DNS64 configuration of a computer.

## SYNTAX

```
Get-NetDnsTransitionConfiguration [-Adapter <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetDnsTransitionConfiguration** cmdlet retrieves the DNS64 configuration of a computer.
DNS64 is described in [RFC 6147](http://tools.ietf.org/html/rfc6147).
DNS64 is used with an IPv6/IPv4 translator to enable client-server communication between an IPv6-only client and an IPv4-only server, without requiring any changes to either the IPv6 or the IPv4 node.

## EXAMPLES

### Example 1: Get the DNS64 configuration
```
PS C:\>Get-NetDnsTransitionConfiguration
```

This example retrieves the DNS64 configuration of a computer.

## PARAMETERS

### -Adapter
Specifies the network adapter from which to retrieve the configuration information.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetDnsTransitionConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.


The **MSFT_NetDnsTransitionConfiguration** object contains the DNS64 configuration.

## NOTES

## RELATED LINKS

[Disable-NetDnsTransitionConfiguration](./Disable-NetDnsTransitionConfiguration.md)

[Enable-NetDnsTransitionConfiguration](./Enable-NetDnsTransitionConfiguration.md)

[Get-NetDnsTransitionMonitoring](./Get-NetDnsTransitionMonitoring.md)

[Reset-NetDnsTransitionConfiguration](./Reset-NetDnsTransitionConfiguration.md)

[Set-NetDnsTransitionConfiguration](./Set-NetDnsTransitionConfiguration.md)

