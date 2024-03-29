---
external help file: MSFT_NetNatTransitionConfiguration.cdxml-help.xml
Module Name: NetworkTransition
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/networktransition/set-netnattransitionconfiguration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetNatTransitionConfiguration
---

# Set-NetNatTransitionConfiguration

## SYNOPSIS
Sets the NAT64 configuration on a computer.

## SYNTAX

### ByName (Default)
```
Set-NetNatTransitionConfiguration [-InstanceName <String[]>] [-PolicyStore <PolicyStore[]>]
 [-Adapter <CimInstance>] [-State <State>] [-InboundInterface <String[]>] [-OutboundInterface <String[]>]
 [-PrefixMapping <String[]>] [-IPv4AddressPortPool <String[]>] [-TcpMappingTimeoutSeconds <UInt32>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetNatTransitionConfiguration -InputObject <CimInstance[]> [-State <State>] [-InboundInterface <String[]>]
 [-OutboundInterface <String[]>] [-PrefixMapping <String[]>] [-IPv4AddressPortPool <String[]>]
 [-TcpMappingTimeoutSeconds <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetNatTransitionConfiguration** sets the NAT64 configuration on a computer.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>$nat64Prefix = "2009:1:2:3:4:5::/96"



PS C:\>$prefixMapping = "$nat64Prefix,0.0.0.0/0"



PS C:\>$portPool = "33.0.0.1,6000-10000"



PS C:\>Set-NetNatTransitionConfiguration -InstanceName NAT64 OutboundInterface corpnet -PrefixMapping $prefixMapping -IPv4AddressPortPool $portPool
```

This example sets the NAT64 configuration for the instance named NAT64.

## PARAMETERS

### -Adapter
Specifies the network adapter on which to apply the NAT64 configuration.

```yaml
Type: CimInstance
Parameter Sets: ByName
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

### -IPv4AddressPortPool
Specifies the list of IPv4 address and port ranges to be used by NAT64 for creating the mappings from the IPv6 source address to the IPv4 target address.
The format is a comma-separated list of \<IPv4 address,Lowport-Highport\>.
Such as `"10.0.0.2,1024-3388","10.0.0.2,4000-49023"`.
The port value must be between 1024 and 65535.
The wildcard character (*) can be specified to use the whole port range, such as `10.0.0.1,*`.

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

### -InboundInterface
Sets the interface on which the NAT64 is listening for the matching incoming IPv6 traffic.

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
Specifies the NAT64 configuration object to set.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InstanceName
Specifies the instance of the NAT64 which is being configured.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OutboundInterface
Sets the interface on which the NAT64 sends the translated IPv4 traffic.

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

### -PolicyStore
Specifies to which policy store the NAT64 configuration is applied.
The acceptable values for this parameter are: Persistent and Active.
If this parameter is not specified, then the cmdlet operates on both active and persistent stores.

```yaml
Type: PolicyStore[]
Parameter Sets: ByName
Aliases: Store
Accepted values: PersistentStore, ActiveStore

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrefixMapping
Sets the list of IPv6 address ranges to be translated by the NAT64.
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

### -State
Sets the enabled state of the NAT64 configuration.

```yaml
Type: State
Parameter Sets: (All)
Aliases: 
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TcpMappingTimeoutSeconds
Specifies the lifetime for a TCP mapping after which it is released by the NAT64.
The minimum value is 1800 seconds. 
                         
The default value is 7200 seconds.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: TcpMappingTimeout

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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetNatTransitionConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-NetNatTransitionConfiguration](./Disable-NetNatTransitionConfiguration.md)

[Enable-NetNatTransitionConfiguration](./Enable-NetNatTransitionConfiguration.md)

[Get-NetNatTransitionConfiguration](./Get-NetNatTransitionConfiguration.md)

[Get-NetNatTransitionMonitoring](./Get-NetNatTransitionMonitoring.md)

[New-NetNatTransitionConfiguration](./New-NetNatTransitionConfiguration.md)

[Remove-NetNatTransitionConfiguration](./Remove-NetNatTransitionConfiguration.md)

