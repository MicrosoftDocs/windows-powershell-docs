---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://docs.microsoft.com/powershell/module/dhcpserver/set-dhcpserverv4failover?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DhcpServerv4Failover

## SYNOPSIS
Modifies the properties of an existing failover relationship.

## SYNTAX

```
Set-DhcpServerv4Failover [-Name] <String> [-AsJob] [-AutoStateTransition <Boolean>]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-Force] [-LoadBalancePercent <UInt32>]
 [-MaxClientLeadTime <TimeSpan>] [-PartnerDown] [-PassThru] [-ReservePercent <UInt32>] [-SharedSecret <String>]
 [-StateSwitchInterval <TimeSpan>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-DhcpServerv4Failover** cmdlet modifies the properties of an existing failover relationship.

If the failover mode of relation is Load Balance mode, then the **LoadBalancePercent**, **MaxClientLeadTime**, **StateSwitchInterval**, **AutoStateTransition**, **SharedSecret**, and **PartnerDown** parameters can be specified.

If the failover mode of relation is Hot Standby mode, then the **ReservePercent**, **MaxClientLeadTime**, **StateSwitchInterval**, **AutoStateTransition**, **SharedSecret**, and **PartnerDown** parameters can be specified.

If the **SharedSecret** parameter is specified, then the message digest authentication is enabled for the failover relationship.

If the **SharedSecret** parameter value is specified as Null, then enableauth will be set to False in the data structure.

If the **SharedSecret** parameter is specified, then confirmation will be sought from the user to transport the shared secret in the clear text on the network.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-DhcpServerv4Failover -ComputerName dhcpserver.contoso.com -Name SFO-SIN-Failover -LoadBalancePercent 70 -MaxClientLeadTime 2:00:00 -AutoStateTransition True -StateSwitchInterval 2:00:00
```

This example modifies the parameters of the Load Balance failover relationship named SFO-SIN-Failover on the computer named dhcpserver.contoso.com as follows: 70% of the client requests will be served by the DHCP server service running on the computer named dhcpserver.contoso.com and 30% of the client requests will be served by the DHCP server service running on the computer named dhcpserver2.contoso.com.
The maximum client lead time for the failover relationship is set to 2 hours.
The automatic state transition from the COMMUNICATION INTERRUPTED state to the PARTNER DOWN state is enabled and the timer for automatic state transition is set to 2 hours.

### EXAMPLE 2
```
PS C:\>Set-DhcpServerv4Failover -ComputerName dhcpserver.contoso.com -Name SFO-SIN-Failover -ReservePercent 10 -MaxClientLeadTime 2:00:00 -AutoStateTransition True -StateSwitchInterval 2:00:00
```

This example modifies the parameters of the Hot Standby failover relationship named SFO-SIN-Failover on computer named dhcpserver.contoso.com as follows: 10% of the free IP addresses in the scopes will be reserved for the standby DHCP server service.
The maximum client lead time for the failover relationship is set to 2 hours.
The automatic state transition from the COMMUNICATION INTERRUPTED state to the PARTNER DOWN state is enabled and the timer for automatic state transition is set to 2 hours.

## PARAMETERS

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

### -AutoStateTransition
Specifies the enabled state for automatic state transition from the COMMUNICATION INTERRUPTED state to the PARTNER DOWN state based on expiration of the timer, using the **StateSwitchInterval** parameter, while in the COMMUNICATION INTERRUPTED state. 
The acceptable values for this parameter are: True or False.
The default value is False. 
Note: This parameter value is set to True, if the **StateSwitchInterval** parameter is specified.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -ComputerName
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the Dynamic Host Configuration Protocol (DHCP) server service.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Specifies, if the **SharedSecret** parameter is specified, that user confirmation is required since the **SharedSecret** parameter value may be transferred in plain text transport in the case of remote management.
Specifying this parameter turns off the user confirmation.

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

### -LoadBalancePercent
Specifies the percentage of DHCP client requests which should be served by the local DHCP server service or the DHCP server service running on the computer specified in the **ComputerName** parameter.
The remaining DHCP client requests would be served by the partner DHCP server service.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxClientLeadTime
Specifies the maximum client lead time for the failover relationship.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of failover relationship for which the properties are modified.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartnerDown
Changes the state of the DHCP server service from COMMUNICATION INTERRUPTED to PARTNER DOWN.

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

### -ReservePercent
Specifies the percentage of the free IPv4 address pool for the scope which should be reserved on the standby DHCP server service. 

In the case of a failover, the IPv4 addresses from this reserved pool on the standby DHCP server service will be leased to new DHCP clients.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharedSecret
Specifies the shared secret to be used for message authentication.
To turn off message authentication, set this parameter value to Null.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StateSwitchInterval
Specifies the time interval for which the DHCP server service should continue to operate in the COMMUNICATION INTERRUPTED state before transitioning to the PARTNER DOWN state.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Failover
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Failover
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4Failover](./Add-DhcpServerv4Failover.md)

[Add-DhcpServerv4FailoverScope](./Add-DhcpServerv4FailoverScope.md)

[Get-DhcpServerv4Failover](./Get-DhcpServerv4Failover.md)

[Invoke-DhcpServerv4FailoverReplication](./Invoke-DhcpServerv4FailoverReplication.md)

[Remove-DhcpServerv4Failover](./Remove-DhcpServerv4Failover.md)

[Remove-DhcpServerv4FailoverScope](./Remove-DhcpServerv4FailoverScope.md)

