---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetNatTransitionConfiguration.cdxml-help.xml
Module Name: NetworkTransition
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networktransition/get-netnattransitionconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetNatTransitionConfiguration
---

# Get-NetNatTransitionConfiguration

## SYNOPSIS
Retrieves the NAT64 configuration of a computer.

## SYNTAX

```
Get-NetNatTransitionConfiguration [-InstanceName <String[]>] [-PolicyStore <PolicyStore[]>]
 [-Adapter <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetNatTransitionConfiguration** cmdlet retrieves the NAT64 configuration of a computer.
NAT64 is described in [RFC 6146](http://tools.ietf.org/html/rfc6147).
NAT64 allows IPv6-only clients to contact IPv4 servers using unicast UDP, TCP, or ICMP.

## EXAMPLES

### Example 1: Get the NAT64 configuration
```
PS C:\>Get-NetNatTransitionConfiguration
```

This command retrieves the NAT64 configuration of a computer.

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

### -InstanceName
Specifies the instance of the NAT64 for which the configuration is being retrieved.
If this parameter is not specified, then the configuration for all of the instances of NAT64 are retrieved.

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

### -PolicyStore
Specifies from which policy store the NAT64 configuration is retrieved.
The acceptable values for this parameter are: Persistent and Active.
If this parameter is not specified, then the cmdlet operates on both active and persistent stores.

```yaml
Type: PolicyStore[]
Parameter Sets: (All)
Aliases: Store
Accepted values: PersistentStore, ActiveStore

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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetNatTransitionConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.


The **MSFT_NetNatTransitionConfiguration** object contains NAT64 configuration information.

## NOTES

## RELATED LINKS

[Disable-NetNatTransitionConfiguration](./Disable-NetNatTransitionConfiguration.md)

[Enable-NetNatTransitionConfiguration](./Enable-NetNatTransitionConfiguration.md)

[Get-NetNatTransitionMonitoring](./Get-NetNatTransitionMonitoring.md)

[New-NetNatTransitionConfiguration](./New-NetNatTransitionConfiguration.md)

[Remove-NetNatTransitionConfiguration](./Remove-NetNatTransitionConfiguration.md)

[Set-NetNatTransitionConfiguration](./Set-NetNatTransitionConfiguration.md)

