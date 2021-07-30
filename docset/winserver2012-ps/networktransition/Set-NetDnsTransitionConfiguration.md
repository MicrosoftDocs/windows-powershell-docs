---
external help file: NetTransition_Cmdlets.xml
Module Name: NetworkTransition
online version: https://docs.microsoft.com/powershell/module/networktransition/set-netdnstransitionconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NetDnsTransitionConfiguration

## SYNOPSIS
Sets the DNS64 configuration on a computer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NetDnsTransitionConfiguration [-AcceptInterface <String[]>] [-Adapter <CimInstance>]
 [-AlwaysSynthesize <Boolean>] [-AsJob] [-CimSession <CimSession[]>] [-ExclusionList <String[]>]
 [-LatencyMilliseconds <UInt32>] [-OnlySendAQuery <Boolean>] [-PassThru] [-PrefixMapping <String[]>]
 [-SendInterface <String[]>] [-State <State>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NetDnsTransitionConfiguration [-AcceptInterface <String[]>] [-AlwaysSynthesize <Boolean>] [-AsJob]
 [-CimSession <CimSession[]>] [-ExclusionList <String[]>] [-LatencyMilliseconds <UInt32>]
 [-OnlySendAQuery <Boolean>] [-PassThru] [-PrefixMapping <String[]>] [-SendInterface <String[]>]
 [-State <State>] [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-NetDnsTransitionConfiguration** sets the DNS64 configuration on a computer.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-NetDnsTransitionConfiguration -State Enabled -Latencymilliseconds 400
```

This example sets the state to enabled and latency to 400 ms for the DNS64 configuration.

## PARAMETERS

### -AcceptInterface
Specifies the interface on which the DNS64 is listening to all of the interfaces classified in the domain profile.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Adapter
Specifies the network adapter on which to set.

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
Specifies that the DNS64 will always send both the response to the AAAA query as well as the synthesized A query response.
If this parameter is set to False, then the DNS64 will send neither the response to the AAAA query nor the synthesized A query response.

```yaml
Type: Boolean
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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
Sets the list of IPv6 address ranges to be excluded from synthesis by the DNS64.
The format is a comma-separated list of IPv6 addresses ranges.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the DNS64 configuration object on which to set.

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
Sets the delay in milliseconds between the AAAA and A query that the DNS64 sends.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: Latency

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnlySendAQuery
Specifies that only A queries should be sent or both A and AAAA queries should be sent.
If this parameter is set to True, then only A queries should be sent.
If this parameter is set to False, then both A and AAAA queries should be sent.

```yaml
Type: Boolean
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
Sets to the list of IPv6 address ranges to be used for synthesis by the DNS64.
The format is a comma-separated list of \<IPv6 prefix,IPv4 subnet\>.
Such as `"69:FF9B::/96,0.0.0.0/0","66:FF9B::/96,192.2.0.0/8"`.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SendInterface
Sets the interface on which the DNS64 sends DNS queries.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State
Sets the enabled state of the DNS64 configuration.

```yaml
Type: State
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

[Reset-NetDnsTransitionConfiguration](./Reset-NetDnsTransitionConfiguration.md)

