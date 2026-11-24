---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerV6OptionValue_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/set-dhcpserverv6optionvalue?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DhcpServerv6OptionValue
---

# Set-DhcpServerv6OptionValue

## SYNOPSIS
Sets an IPv6 option value at the server, scope, or reservation level.

## SYNTAX

### OptionIds (Default)
```
Set-DhcpServerv6OptionValue [-PassThru] [-Force] [[-Prefix] <IPAddress>] [-UserClass <String>]
 [-ComputerName <String>] [-ReservedIP <IPAddress>] [-Value] <String[]> [-OptionId] <UInt32>
 [-VendorClass <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### CommonOptions
```
Set-DhcpServerv6OptionValue [-PassThru] [-Force] [[-Prefix] <IPAddress>] [-UserClass <String>]
 [-DnsServer <IPAddress[]>] [-DomainSearchList <String[]>] [-InfoRefreshTime <UInt32>] [-ComputerName <String>]
 [-ReservedIP <IPAddress>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-DhcpServerv6OptionValue** cmdlet sets an IPv6 option value at the server, scope, or reservation level.
The definition for the option must already exist on the Dynamic Host Configuration Protocol (DHCP) server service.
If you specify the *ReservedIP* parameter, the option values are set at the reservation level.
If you specify only the *Prefix* parameter, the option values are set at the scope level.
If you specify neither the *Prefix* nor *ReservedIP* parameter, the option values are set at the server level.
The *Prefix* and *ReservedIP* parameters cannot both be specified.

If you specify the *VendorClass* parameter, this cmdlet sets the option value for the specified vendor class.
If you specify the *UserClass* parameter, this cmdlet sets the option value for the specified user class.

## EXAMPLES

### Example 1: Set server level option values
```
PS C:\> Set-DhcpServerv6OptionValue -ComputerName "dhcpserver.contoso.com" -DnsServer 2001:4898:7020:1020::2 -DomainSearchList "contoso.com"
```

This example sets the DHCPv6 server level option values for DNS server and domain search list options.

### Example 2: Set option values for a scope
```
PS C:\> Set-DhcpServerv6OptionValue -ComputerName "dhcpserver.contoso.com" -Prefix 2001:4898:7020:1020:: -DnsServer 2001:4898:7020:1020::2 -DomainSearchList "contoso.com"
```

This example sets the DHCPv6 option values for DNS server and domain search list options on the scope 2001:4898:7020:1020::.

### Example 3: Set service-wide option value for DNS server
```
PS C:\> Set-DhcpServerv6OptionValue -ComputerName "dhcpserver.contoso.com" -OptionId 23 -Value "2001:4898:7020:1020::2"
```

This example sets server-wide DHCPv6 option value for option ID 23, or the DNS server.

### Example 4: Set option value for DNS server for a scope
```
PS C:\> Set-DhcpServerv6OptionValue -ComputerName "dhcpserver.contoso.com" -Prefix 2001:4898:7020:1020:: -OptionId 23 -Value "2001:4898:7020:1020::2"
```

This example sets the DHCPv6 option value for option ID 23, or the DNS server, for the specified DHCPv6 scope.

### Example 5: Set option value for DNS server for a reservation
```
PS C:\> Set-DhcpServerv6OptionValue -ComputerName "dhcpserver.contoso.com" -ReservedIP 2001:4898:7020:1020::5 -OptionId 23 -Value "2001:4898:7020:1020::2"
```

This example sets the DHCPv6 option value for option ID 23, or the DNS server, for the specified reservation.

### Example 6: Set a vendor class specific option value
```
PS C:\> Set-DhcpServerv6OptionValue -ComputerName "dhcpserver.contoso.com" -Prefix 2001:4898:7020:1020:: -VendorClass "MSUCClient" -OptionId 5 -Value "6874747073"
```

This example sets the vendor class specific DHCPv6 option value configured on the specified scope for the specified vendor class named MSUCClient.

### Example 7: Set a user class specific option value for DNS server
```
PS C:\> Set-DhcpServerv6OptionValue -ComputerName "dhcpserver.contoso.com" -Prefix 2001:4898:7020:1020:: -UserClass "LabComputer" -OptionId 23 -Value "2001:4898:7020:1020::20"
```

This example sets the user class specific DHCPv6 option value for option ID 23, or the DNS server, on the specified scope for the specified user class.

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
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer that runs the DHCP server service.

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

### -DnsServer
Specifies one or more values for the DNS server option.

```yaml
Type: IPAddress[]
Parameter Sets: CommonOptions
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DomainSearchList
Specifies one or more values for the domain search list option.

```yaml
Type: String[]
Parameter Sets: CommonOptions
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Specifies that the DNS server validation is skipped.
This parameter is applicable only if the *DNSServer* parameter or option ID 23 is specified.

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

### -InfoRefreshTime
Specifies the value for the information refresh option.
This parameter value specifies an upper bound for how long a client waits before refreshing information retrieved from DHCPv6 server.
This parameter is used with stateless DHCPv6 as there are no addresses or other entities with lifetimes that can tell the client when to contact the DHCPv6 server to refresh its configuration.

```yaml
Type: UInt32
Parameter Sets: CommonOptions
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OptionId
Specifies the numeric identifier (ID) of the option for which a value is set.

```yaml
Type: UInt32
Parameter Sets: OptionIds
Aliases:

Required: True
Position: 1
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

### -Prefix
Specifies the IPv6 subnet prefix of the scope on which the option value is set.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReservedIP
Specifies the IPv6 address of the reservation for which the option value is set.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: IPAddress

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

### -UserClass
Specifies the option value for the specified user class.

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

### -Value
Specifies the value to set for the option.

```yaml
Type: String[]
Parameter Sets: OptionIds
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VendorClass
Specifies the option value for the specified vendor class.

```yaml
Type: String
Parameter Sets: OptionIds
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6OptionDefinition
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6OptionValue
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Reservation
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6OptionValue
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DhcpServerv6OptionValue](./Get-DhcpServerv6OptionValue.md)

[Remove-DhcpServerv6OptionValue](./Remove-DhcpServerv6OptionValue.md)

