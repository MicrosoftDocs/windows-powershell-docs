---
external help file: DhcpServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 73E31BF4-D1DD-4517-9606-4FF4F22DD67C
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Set-DhcpServerv6OptionValue

## SYNOPSIS
Sets an IPv6 option value at the server, scope, or reservation level.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-DhcpServerv6OptionValue [-OptionId] <UInt32> [-Value] <String[]> [[-Prefix] <IPAddress>] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-Force] [-PassThru] [-ReservedIP <IPAddress>]
 [-ThrottleLimit <Int32>] [-UserClass <String>] [-VendorClass <String>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-DhcpServerv6OptionValue [[-Prefix] <IPAddress>] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-DnsServer <IPAddress[]>] [-DomainSearchList <String[]>] [-Force]
 [-InfoRefreshTime <UInt32>] [-PassThru] [-ReservedIP <IPAddress>] [-ThrottleLimit <Int32>]
 [-UserClass <String>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-DhcpServerv6OptionValue** cmdlet sets an IPv6 option value at the server, scope, or reservation level.
The definition for the option must already exist on the Dynamic Host Configuration Protocol (DHCP) server service.
If the **ReservedIP** parameter is specified, then the option values are set at the reservation level.
If only the **Prefix** parameter is specified, then the option values are set at the scope level.
If neither the **Prefix** nor **ReservedIP** parameter is specified, then the option values are set at the server level.
The **Prefix** and **ReservedIP** parameters cannot both be specified.

If the **VendorClass** parameter is specified, then this cmdlet sets the option value for the specified vendor class.
If the **UserClass** parameter is specified, then this cmdlet sets the option value for the specified user class.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-DhcpServerv6OptionValue -ComputerName dhcpserver.contoso.com -DnsServer 2001:4898:7020:1020::2 -DomainSearchList contoso.com
```

This example sets the DHCPv6 server level option values for DNS server and domain search list options.

### EXAMPLE 2
```
PS C:\>Set-DhcpServerv6OptionValue -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020:: -DnsServer 2001:4898:7020:1020::2 -DomainSearchList contoso.com
```

This example sets the DHCPv6 option values for DNS server and domain search list options on the scope 2001:4898:7020:1020::.

### EXAMPLE 3
```
PS C:\>Set-DhcpServerv6OptionValue -ComputerName dhcpserver.contoso.com -OptionId 23 -Value 2001:4898:7020:1020::2
```

This example sets server-wide DHCPv6 option value for option ID 23, or the DNS server.

### EXAMPLE 4
```
PS C:\>Set-DhcpServerv6OptionValue -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020:: -OptionId 23 -Value 2001:4898:7020:1020::2
```

This example sets the DHCPv6 option value for option ID 23, or the DNS server, for the specified DHCPv6 scope.

### EXAMPLE 5
```
PS C:\>Set-DhcpServerv6OptionValue -ComputerName dhcpserver.contoso.com -ReservedIP 2001:4898:7020:1020::5 -OptionId 23 -Value 2001:4898:7020:1020::2
```

This example sets the DHCPv6 option value for option ID 23, or the DNS server, for the specified reservation.

### EXAMPLE 6
```
PS C:\>Set-DhcpServerv6OptionValue -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020:: -VendorClass MSUCClient -OptionId 5 -Value 6874747073
```

This example sets the vendor-class-specific DHCPv6 option value configured on the specified scope for the specified vendor class named MSUCClient.

### EXAMPLE 7
```
PS C:\>Set-DhcpServerv6OptionValue -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020:: -UserClass LabComputer -OptionId 23 -Value 2001:4898:7020:1020::20
```

This example sets the user-class-specific DHCPv6 option value for option ID 23, or the DNS server, on the specified scope for the specified user class.

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

### -DnsServer
Specifies one or more values for the DNS server option.

```yaml
Type: IPAddress[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Specifies that the DNS server validation should not be performed.
This parameter is applicable only if the **DNSServer** parameter or option ID 23 is specified.

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
This parameter value specifies an upper bound for how long a client should wait before refreshing information retrieved from DHCPv6 server.
This parameter is used with stateless DHCPv6 as there are no addresses or other entities with lifetimes that can tell the client when to contact the DHCPv6 server to refresh its configuration.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OptionId
Specifies the numeric identifier (ID) of the option for which a value is being set.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Specifies the IPv6 subnet prefix of the scope on which the option value is being set.

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
Specifies the IPv6 address of the reservation for which the option value is being set.

```yaml
Type: IPAddress
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
Specifies the value being set for the option.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

