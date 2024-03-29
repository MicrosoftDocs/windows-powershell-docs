---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://learn.microsoft.com/powershell/module/dhcpserver/set-dhcpserverv4scope?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DhcpServerv4Scope

## SYNOPSIS
Sets the properties of an existing IPv4 scope on the Dynamic Host Configuration Protocol (DHCP) server service.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-DhcpServerv4Scope [-ScopeId] <IPAddress> [-ActivatePolicies <Boolean>] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-Delay <UInt16>] [-Description <String>]
 [-LeaseDuration <TimeSpan>] [-MaxBootpClients <UInt32>] [-Name <String>] [-NapEnable <Boolean>]
 [-NapProfile <String>] [-PassThru] [-State <String>] [-SuperscopeName <String>] [-ThrottleLimit <Int32>]
 [-Type <String>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-DhcpServerv4Scope [-ScopeId] <IPAddress> [-ActivatePolicies <Boolean>] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-Delay <UInt16>] [-Description <String>]
 [-LeaseDuration <TimeSpan>] [-MaxBootpClients <UInt32>] [-Name <String>] [-NapEnable <Boolean>]
 [-NapProfile <String>] [-PassThru] [-State <String>] [-SuperscopeName <String>] [-ThrottleLimit <Int32>]
 [-Type <String>] -EndRange <IPAddress> -StartRange <IPAddress> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-DhcpServerv4Scope** cmdlet sets the properties of an existing IPv4 scope on the Dynamic Host Configuration Protocol (DHCP) server service.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-DhcpServerv4Scope -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -Name "Ext Lab Net VLAN100" -State Active -LeaseDuration 4.00:00:00
```

This example sets the name of the specified DHCPv4 scope to Ext Lab Net VLAN100, activates the scope, and sets the lease duration to 4 days.

## PARAMETERS

### -ActivatePolicies
Specifies the enabled state for the policy enforcement on the scope.
The acceptable values for this parameter are: True or False.

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

### -Delay
Specifies the time, in milliseconds, by which the DHCP server service should delay sending a response to the clients.
This parameter should be used on the secondary DHCP server service in a split scope configuration.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies the description to set for the scope.

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

### -EndRange
Specifies the ending address of the IPv4 range to set for the scope.
If a new IPv4 range is being set, then the previously set IPv4 range of the scope is discarded.

```yaml
Type: IPAddress
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LeaseDuration
Specifies the duration of the IPv4 address lease to give for the clients of the scope.

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

### -MaxBootpClients
Specifies the maximum number of Bootp clients permitted to get an IP address lease from the scope.
This parameter can only be used if the **Type** parameter value is set to Both.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name to set for the scope.

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

### -NapEnable
Specifies the enabled state for network access protection (NAP) for the scope.
The acceptable values for this parameter are: True or False.

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

### -NapProfile
Specifies the name of the NAP profile for clients in the scope.
The NAP profile refers to the Microsoft Service Class which is a condition used in network policies on the network policy server (NPS).
This parameter can only be used if the **NapEnable** parameter value is set to True.

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

### -ScopeId
Specifies the scope identifier (ID), in IPv4 address format, for which the properties are being set.

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

### -StartRange
Specifies the starting address of the IPv4 range to set for the scope.
If a new IP range is being set, then the previously set IP range of the scope is discarded.

```yaml
Type: IPAddress
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State
Specifies the state of the scope.
The acceptable values for this parameter are: Active and InActive.

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

### -SuperscopeName
Specifies the name of the superscope to which this scope is added.

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

### -Type
Specifies the type of the scope.
The acceptable values for this parameter are: DHCP, BootP, and Both.
The type of the scope determines if the DHCP server service responds to only DHCP client requests, only BootP client requests, or Both types of clients.

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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4Scope](./Add-DhcpServerv4Scope.md)

[Get-DhcpServerv4Scope](./Get-DhcpServerv4Scope.md)

[Get-DhcpServerv4ScopeStatistics](./Get-DhcpServerv4ScopeStatistics.md)

[Remove-DhcpServerv4Scope](./Remove-DhcpServerv4Scope.md)

