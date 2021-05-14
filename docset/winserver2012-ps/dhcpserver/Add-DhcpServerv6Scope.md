---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://docs.microsoft.com/powershell/module/dhcpserver/add-dhcpserverv6scope?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-DhcpServerv6Scope

## SYNOPSIS
Adds an IPv6 scope to the Dynamic Host Configuration Protocol (DHCP) server service with the specified parameters.

## SYNTAX

```
Add-DhcpServerv6Scope [-Prefix] <IPAddress> [-Name] <String> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-Description <String>] [-PassThru] [-Preference <UInt16>]
 [-PreferredLifetime <TimeSpan>] [-State <String>] [-T1 <TimeSpan>] [-T2 <TimeSpan>] [-ThrottleLimit <Int32>]
 [-ValidLifeTime <TimeSpan>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-DhcpServerv6Scope** cmdlet adds an IPv6 scope to the Dynamic Host Configuration Protocol (DHCP) server service with the specified parameters.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Add-DhcpServerv6Scope -Prefix 2001:4898:7020:1020:: -Name "IPv6 Lab-4 Network"
```

The above command adds a DHCPv6 scope with subnet prefix 2001:4898:7020:1020:: and specified scope name to the DHCP server running on local computer.

### EXAMPLE 2
```
PS C:\>Add-DhcpServerv6Scope -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020:: -Name "IPv6 Lab-4 Network" -PreferredLifeTime 4.00:00:00 -ValidLifeTime 6.00:00:00 -State Inactive
```

This example adds an inactive DHCPv6 scope with the subnet prefix 2001:4898:7020:1020::, specifies the scope name, sets the preferred lifetime to 4 days, and sets the valid lifetime to 6 days to the DHCP server service running on the computer named dhcpserver.contoso.com.

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

### -Description
Specifies the description associated with the scope.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name associated with the scope.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

### -Preference
Specifies the value for the preference field to be used by the DHCP server service while responding to clients in this subnet.
The acceptable values for this parameter are: 0 through 255. 

The default value is 0.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 0
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PreferredLifetime
Specifies the preferred life time of the IPv6 address leased by the DHCP server service.
The default value is 8 days. 

This parameter value should be same or less than the **ValidLifeTime** parameter value.

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

### -Prefix
Specifies the IPv6 prefix of the scope being added.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State
Specifies the state of the scope.
The acceptable values for this parameter are: Enabled or Disabled.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -T1
Specifies the lease renewal time.
The default value is 4 days.
The DHCP client is expected to use a unicast message to renew the lease at the time specified by this parameter value from the same DHCP server service from which DHCP client had initially obtained the lease. 

This parameter value should be less than the **T2** and **PreferredLifetime** parameter values.

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

### -T2
Specifies the lease rebind time.
The default value is 6.4 days.
The DHCP client is expected to use a multi-cast message to renew the lease at the time equal to this parameter value from any DHCP server service if the renewal attempt at time specified by the **T1** parameter fails. 

This parameter value should be greater than the **T1** parameter value and less than the **PreferredLifetime** parameter value.

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

### -ValidLifeTime
Specifies the valid life time of the IPv6 address leased by the DHCP server service.
The default value is `12` days. 

This parameter value should be same or greater than the **PreferredLifetime** parameter value.

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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DhcpServerv6Scope](./Get-DhcpServerv6Scope.md)

[Get-DhcpServerv6ScopeStatistics](./Get-DhcpServerv6ScopeStatistics.md)

[Remove-DhcpServerv6Scope](./Remove-DhcpServerv6Scope.md)

[Set-DhcpServerv6Scope](./Set-DhcpServerv6Scope.md)

