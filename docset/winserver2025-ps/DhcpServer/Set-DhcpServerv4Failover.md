---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerv4Failover_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/set-dhcpserverv4failover?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DhcpServerv4Failover
---

# Set-DhcpServerv4Failover

## SYNOPSIS
Modifies the properties of an existing failover relationship.

## SYNTAX

```
Set-DhcpServerv4Failover [-ComputerName <String>] [-Name] <String> [-AutoStateTransition <Boolean>]
 [-MaxClientLeadTime <TimeSpan>] [-SharedSecret <String>] [-StateSwitchInterval <TimeSpan>] [-PartnerDown]
 [-Force] [-LoadBalancePercent <UInt32>] [-ReservePercent <UInt32>] [-PassThru] [-Mode <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DhcpServerv4Failover** cmdlet modifies the properties of an existing failover relationship.

If the failover mode of relation is load balance or is being changed to load balance, the *LoadBalancePercent*, *MaxClientLeadTime*, *StateSwitchInterval*, *AutoStateTransition*, and *SharedSecret* parameters can be specified.

If the failover mode of relation is hot standby or is being changed to hot standby, the *ReservePercent*, *MaxClientLeadTime*, *StateSwitchInterval*, *AutoStateTransition*, and *SharedSecret* parameters can be specified.

If the *SharedSecret* parameter value is $Null, **enableauth** is set to $False in the data structure.
If the *SharedSecret* parameter is not $Null, **enableauth** is set to $True in the data structure.

If the *SharedSecret* parameter is specified, confirmation is sought from the user to transport the shared secret in the clear text on the network.

If you specify the *Mode* parameter to change the mode of the failover relationship, default confirmation is sought.

## EXAMPLES

### Example 1: Modify parameters of a load balance failover relationship
```
PS C:\> Set-DhcpServerv4Failover -ComputerName "dhcpserver.contoso.com" -Name "SFO-SIN-Failover" -LoadBalancePercent 70 -MaxClientLeadTime 2:00:00 -AutoStateTransition $True -StateSwitchInterval 2:00:00
```

This example modifies the parameters of the load balance failover relationship named SFO-SIN-Failover on the computer named dhcpserver.contoso.com as follows: 70% of the client requests will be served by the DHCP server service that runs on the computer named dhcpserver.contoso.com and 30% of the client requests will be served by the DHCP server service that runs on the computer named dhcpserver2.contoso.com.
The maximum client lead time for the failover relationship is set to 2 hours.
The automatic state transition from the COMMUNICATION INTERRUPTED state to the PARTNER DOWN state is enabled and the timer for automatic state transition is set to 2 hours.

### Example 2: Modify parameters of a load balance failover relationship with reserve
```
PS C:\> Set-DhcpServerv4Failover -ComputerName "dhcpserver.contoso.com" -Name "SFO-SIN-Failover" -ReservePercent 10 -MaxClientLeadTime 2:00:00 -AutoStateTransition $True -StateSwitchInterval 2:00:00
```

This example modifies the parameters of the hot standby failover relationship named SFO-SIN-Failover on computer named dhcpserver.contoso.com as follows: 10% of the free IP addresses in the scopes will be reserved for the standby DHCP server service.
The maximum client lead time for the failover relationship is set to 2 hours.
The automatic state transition from the COMMUNICATION INTERRUPTED state to the PARTNER DOWN state is enabled and the timer for automatic state transition is set to 2 hours.

### Example 3: Change the mode of a failover relationship
```
PS C:\> Set-DhcpServerv4Failover -Name "SFO-SIN-Failover" -ComputerName "dhcpserver.contoso.com" -Mode "LoadBalance" -LoadBalancePercent 60
```

This example changes the mode of the failover relationship SFO-SIN-Failover to *LoadBalance*.
The computer named dhcpserver.contoso.com serves 60 percent of the clients.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Specifies the enabled state for automatic state transition from the COMMUNICATION INTERRUPTED state to the PARTNER DOWN state based on expiration of the timer, by using the *StateSwitchInterval* parameter, while in the COMMUNICATION INTERRUPTED state.
The default value is $False.

This parameter value is $True, if the *StateSwitchInterval* parameter is specified.

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

### -ComputerName
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer that runs the Dynamic Host Configuration Protocol (DHCP) server service.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

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

### -Force
Specifies, if the *SharedSecret* parameter is specified, that user confirmation is required because the *SharedSecret* parameter value may be transferred in plain text transport for remote management.
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
Specifies the percentage of DHCP client requests which should be served by the local DHCP server service or the DHCP server service that runs on the computer specified in the *ComputerName* parameter.
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

### -Mode
Specifies a mode for the failover relationship.
The acceptable values for this parameter are:

- HotStandby.
Changes the mode to hot standby.
- LoadBalance.
Changes the mode to load balance.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: LoadBalance, HotStandby

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
To turn off message authentication, set this parameter value to $Null.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

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

