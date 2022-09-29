---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://learn.microsoft.com/powershell/module/dhcpserver/add-dhcpserverv4failover?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-DhcpServerv4Failover

## SYNOPSIS
Adds a new IPv4 failover relationship on the Dynamic Host Configuration Protocol (DHCP) server service.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-DhcpServerv4Failover [-Name] <String> [-ScopeId] <IPAddress[]> [-PartnerServer] <String> [-AsJob]
 [-AutoStateTransition <Boolean>] [-CimSession <CimSession[]>] [-ComputerName <String>] [-Force]
 [-LoadBalancePercent <UInt32>] [-MaxClientLeadTime <TimeSpan>] [-PassThru] [-SharedSecret <String>]
 [-StateSwitchInterval <TimeSpan>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Add-DhcpServerv4Failover [-Name] <String> [-ScopeId] <IPAddress[]> [-PartnerServer] <String> [-AsJob]
 [-AutoStateTransition <Boolean>] [-CimSession <CimSession[]>] [-ComputerName <String>] [-Force]
 [-MaxClientLeadTime <TimeSpan>] [-PassThru] [-ReservePercent <UInt32>] [-ServerRole <String>]
 [-SharedSecret <String>] [-StateSwitchInterval <TimeSpan>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-DhcpServerv4Failover** cmdlet adds a new IPv4 failover relationship to a Dynamic Host Configuration Protocol (DHCP) server service.
The first parameter set adds a failover relationship with load balance mode.
The second parameter set adds the failover relationship in hot-standby mode.

This cmdlet creates the failover relationship on both of the DHCP server services with the specified parameters.
The **ScopeId** parameter value specified on the source DHCP server service, or local computer running the DHCP server service is identically setup on the partner DHCP server service.

If the **SharedSecret** parameter is specified, message digest authentication will be automatically turned on for the newly created failover relationship.

By default, user confirmation will be sought if the **SharedSecret** parameter is specified.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Add-DhcpServerv4Failover -ComputerName dhcpserver.contoso.com -Name SFO-SIN-Failover -PartnerServer dhcpserver2.contoso.com -ScopeId 10.10.10.0,20.20.20.0 -SharedSecret "sEcReT"
```

This example creates a load balance, or active-active, failover relationship between the DHCP server services running on the computers named dhcpserver.contoso.com and dhcpserver2.contoso.com with the scopes 10.10.10.0 and 20.20.20.0 present on the DHCP server service running on  the computer named dhcpserver.contoso.com added to the failover relationship.
These scopes will be created on the partner DHCP server service running on the computer named dhcpserver2.contoso.com as part of the failover relationship creation.
Message authentication is enabled for the server-to-server message exchange with the specified shared secret.

### EXAMPLE 2
```
PS C:\>Add-DhcpServerv4Failover -ComputerName dhcpserver.contoso.com -Name SFO-SIN-Failover -PartnerServer dhcpserver2.contoso.com -ServerRole Standby -ScopeId 10.10.10.0,20.20.20.0
```

This example creates a hot standby, or active-passive, failover relationship between the DHCP server services running on the computers named dhcpserver.contoso.com and dhcpserver2.contoso.com with the scopes 10.10.10.0 and 20.20.20.0 present on the DHCP server service running on the computer named dhcpserver.contoso.com added to the failover relationship.
These scopes will be created on the partner DHCP server service running on the computer named dhcpserver2.contoso.com as part of the failover relationship creation.
The DHCP server service running on the computer named dhcpserver.contoso.com will be the standby DHCP server service and the DHCP server service running on the computer named dhcpserver2.contoso.com will be the active DHCP server service in the failover relationship.

### EXAMPLE 3
```
PS C:\>Add-DhcpServerv4Failover -ComputerName dhcpserver.contoso.com -Name SFO-SIN-Failover -PartnerServer dhcpserver2.contoso.com -ScopeId 10.10.10.0,20.20.20.0 -LoadBalancePercent 70 -MaxClientLeadTime 2:00:00 -AutoStateTransition $true -StateSwitchInterval 2:00:00
```

This example creates a load balance, or active-active, failover relationship between the DHCP server services running on the computer named dhcpserver.contoso.com and dhcpserver2.contoso.com with the scopes 10.10.10.0 and 20.20.20.0 present on the DHCP server service running on the computer named dhcpserver.contoso.com added to the failover relationship.
These scopes will be created on the partner DHCP server service running on the computer named dhcpserver2.contoso.com as part of the failover relationship creation.
70% of the client requests will be served by DHCP server service running on the computer named dhcpserver.contoso.com and 30% by the DHCP server service running on the computer named dhcpserver2.contoso.com.
The maximum client lead time for the failover relationship is set to 2 hours.
The automatic state transition from the COMMUNICATION INTERRUPTED state to the PARTNER DOWN state is turned on and the timer for automatic state transition is set to 2 hours.

### EXAMPLE 4
```
PS C:\>Add-DhcpServerv4Failover -ComputerName dhcpserver.contoso.com -Name SFO-SIN-Failover -PartnerServer dhcpserver2.contoso.com -ScopeId 10.10.10.0,20.20.20.0 -ReservePercent 10 -MaxClientLeadTime 2:00:00 -AutoStateTransition $true -StateSwitchInterval 2:00:00
```

This example creates a hot standby, or Active-Passive, failover relationship between the DHCP server service running on the computer named dhcpserver.contoso.com and dhcpserver2.contoso.com with the scopes 10.10.10.0 and 20.20.20.0 present on the DHCP server service running on the computer named dhcpserver.contoso.com added to the failover relationship.
These scopes will be created on the partner DHCP server service running on the computer named dhcpserver2.contoso.com as part of the failover relationship creation.
The DHCP server service running on the computer named dhcpserver2.contoso.com will be standby DHCP server service and the DHCP server service running on the computer named dhcpserver.contoso.com will be the active DHCP server service in the failover relationship.
10% of the free IP addresses in the scopes will be reserved for the standby DHCP server service.
The maximum client lead time for the failover relationship is set to 2 hours.
The automatic state transition from the COMMUNICATED INTERUPTED state to the PARTNER DOWN state is turned on and the timer for automatic state transition is set to 2 hours.

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

If the **StateSwitchInterval** parameter is specified, then this parameter is automatically set to True.

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
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the DHCP server service.

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
Specifies that, if the **SharedSecret** parameter is specified, the user confirmation is required since the **SharedSecret** parameter value may be transferred in plain text transport in the case of remote management.
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
The remaining requests would be served by the partner DHCP server service. 

The default value is 50%.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxClientLeadTime
Specifies the maximum client lead time for the failover relationship.
The default value is 1 hour.

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
Specifies the name of the failover relationship to create.

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

### -PartnerServer
Specifies the IPv4 address, or host name, of the partner DHCP server service with which the failover relationship is created.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Specifies the percentage of free IPv4 addresses in the IPv4 address pool of the scope which should be reserved on the standby DHCP server service. 

In the case of a failover, the IPv4 address from this reserved pool on the standby DHCP server service will be leased to new DHCP clients. 

The default value is 5%.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScopeId
Specifies the scope identifiers, in IPv4 address format, which are to be added to the failover relationship.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerRole
Specifies the role of the local DHCP server service in the hot standby mode.
The acceptable values for this parameter are: Active or Standby. 

The default value is Active for the local DHCP server service, such as the partner DHCP server service that is specified will be a standby DHCP server service.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharedSecret
Specifies the shared secret to be used for message digest authentication.
If not specified, then the message digest authentication is turned off.

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
Specifies the time interval for which the DHCP server service operates in the COMMUNICATION INTERRUPTED state before transitioning to the PARTNER DOWN state.

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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Failover
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-Content](https://go.microsoft.com/fwlink/p/?LinkID=204574)

[Add-DhcpServerv4FailoverScope](./Add-DhcpServerv4FailoverScope.md)

[Get-DhcpServerv4Failover](./Get-DhcpServerv4Failover.md)

[Invoke-DhcpServerv4FailoverReplication](./Invoke-DhcpServerv4FailoverReplication.md)

[Remove-DhcpServerv4Failover](./Remove-DhcpServerv4Failover.md)

[Remove-DhcpServerv4FailoverScope](./Remove-DhcpServerv4FailoverScope.md)

[Set-DhcpServerv4Failover](./Set-DhcpServerv4Failover.md)

