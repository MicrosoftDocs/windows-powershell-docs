---
external help file: NetTransition_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 23BD4FA5-B1E8-44C9-B1DF-308A2F9CFAC0
manager: dansimp
---

# Reset-NetDnsTransitionConfiguration

## SYNOPSIS
Resets the DNS64 configuration on a computer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Reset-NetDnsTransitionConfiguration [-AcceptInterface] [-Adapter <CimInstance>] [-AlwaysSynthesize] [-AsJob]
 [-CimSession <CimSession[]>] [-ExclusionList] [-LatencyMilliseconds] [-OnlySendAQuery] [-PassThru]
 [-PrefixMapping] [-SendInterface] [-State] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Reset-NetDnsTransitionConfiguration [-AcceptInterface] [-AlwaysSynthesize] [-AsJob]
 [-CimSession <CimSession[]>] [-ExclusionList] [-LatencyMilliseconds] [-OnlySendAQuery] [-PassThru]
 [-PrefixMapping] [-SendInterface] [-State] [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Reset-NetDnsTransitionConfiguration** resets the settings for the DNS64 configuration with the default settings.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Reset-NetDnsTransitionConfiguration -State -Latencymilliseconds
```

This example resets the state and latency of the DNS64 configuration.

## PARAMETERS

### -AcceptInterface
Resets the interface on which the DNS64 is listening to all interfaces classified in the Domain profile.

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

### -Adapter
Specifies the network adapter on which to apply the reset.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AlwaysSynthesize
Specifies that the DNS64 will always synthesize responses by sending both the AAAA response and well as the synthesized A response, when set to False.

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

### -ExclusionList
Resets to the list of IPv6 address ranges to be excluded from synthesis by the DNS64 to `::ffff:0:0/96`.

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

### -InputObject
Specifies the DNS64 configuration object to reset.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LatencyMilliseconds
Resets to the default value of 300 ms for the delay between the AAAA and A query that the DNS64 sends.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: Latency

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnlySendAQuery
Specifies that both A and AAAA queries will be sent, when set to False.

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

### -PrefixMapping
Resets to the list of IPv6 address ranges to be excluded from synthesis by the DNS64 to `64:FF9B::/96`, `0.0.0.0/0`.

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

### -SendInterface
Resets the interface on which the DNS64 sends DNS queries to all interface classified in the Domain profile.

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

### -State
Resets the state of the DNS64 configuration to disabled.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetDnsTransitionConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-NetDnsTransitionConfiguration](./Disable-NetDnsTransitionConfiguration.md)

[Enable-NetDnsTransitionConfiguration](./Enable-NetDnsTransitionConfiguration.md)

[Get-NetDnsTransitionConfiguration](./Get-NetDnsTransitionConfiguration.md)

[Get-NetDnsTransitionMonitoring](./Get-NetDnsTransitionMonitoring.md)

[Set-NetDnsTransitionConfiguration](./Set-NetDnsTransitionConfiguration.md)

