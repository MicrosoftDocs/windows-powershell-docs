---
external help file: NetTransition_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 9625726C-C682-46AD-8D3B-6C8252697EC5
manager: dansimp
---

# Get-NetDnsTransitionConfiguration

## SYNOPSIS
Retrieves the DNS64 configuration of a computer.

## SYNTAX

```
Get-NetDnsTransitionConfiguration [-Adapter <CimInstance>] [-AsJob] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NetDnsTransitionConfiguration** cmdlet retrieves the DNS64 configuration of a computer.
DNS64 is described in the RFC 6147http://tools.ietf.org/html/rfc6147.
DNS64 is used with an IPv6/IPv4 translator to enable client-server communication between an IPv6-only client and an IPv4-only server, without requiring any changes to either the IPv6 or the IPv4 node.

## EXAMPLES

### EXAMPLE 1
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
Aliases: 

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

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetDnsTransitionConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The MSFT_NetDnsTransitionConfiguration object contains the DNS64 configuration.

## NOTES

## RELATED LINKS

[Disable-NetDnsTransitionConfiguration](./Disable-NetDnsTransitionConfiguration.md)

[Enable-NetDnsTransitionConfiguration](./Enable-NetDnsTransitionConfiguration.md)

[Get-NetDnsTransitionMonitoring](./Get-NetDnsTransitionMonitoring.md)

[Reset-NetDnsTransitionConfiguration](./Reset-NetDnsTransitionConfiguration.md)

[Set-NetDnsTransitionConfiguration](./Set-NetDnsTransitionConfiguration.md)

