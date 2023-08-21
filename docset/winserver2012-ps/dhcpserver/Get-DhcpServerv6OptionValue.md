---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://learn.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv6optionvalue?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-DhcpServerv6OptionValue

## SYNOPSIS
Returns the IPv6 option values for one or more IPv6 options either for a specific reserved IP, scope or, server level.

## SYNTAX

```
Get-DhcpServerv6OptionValue [[-OptionId] <UInt32[]>] [[-Prefix] <IPAddress>] [-All] [-AsJob] [-Brief]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-ReservedIP <IPAddress>] [-ThrottleLimit <Int32>]
 [-UserClass <String>] [-VendorClass <String>]
```

## DESCRIPTION
The **Get-DhcpServerv6OptionValue** cmdlet returns the IPv6 option values for one or more IPv6 options either for a specific reserved IP, scope, or server level.
The option identifier (ID) can be a standard option or for a specified vendor class.
If the **OptionId** parameter is not specified, then all option values at the requested level, such as reservation, scope, server, are returned.

If the **ReservedIP** parameter is specified, then the option values set at the reservation level are returned.
If the **Prefix** parameter is specified, then the option values set at the specified scope level are returned.
If neither the **Prefix** nor the **ReservedIP** parameter is specified, then the option values set at the server level are returned.
The **Prefix** and **ReservedIP** parameters cannot both be specified.

If neither the **VendorClass** nor the **UserClass** parameter is specified, then this cmdlet returns the standard option values.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DhcpServerv6OptionValue -ComputerName dhcpserver.contoso.com
```

This example gets all of the standard DHCPv6 option values, non-class specific, configured at the server level.

### EXAMPLE 2
```
PS C:\>Get-DhcpServerv6OptionValue -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020::
```

This example gets all of the standard DHCPv6 option values, non-class specific, configured for the specified scope.

### EXAMPLE 3
```
PS C:\>Get-DhcpServerv6OptionValue -ComputerName dhcpserver.contoso.com -ReservedIP 2001:4898:7020:1020::5
```

This example gets all of the standard DHCPv6 option values, non-class specific, configured for the specified reservation.

### EXAMPLE 4
```
PS C:\>Get-DhcpServerv6OptionValue -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020:: -VendorClass MSUCClient
```

This example gets all of the vendor class specific DHCPv6 option values configured on the specified scope for the specified vendor class.

### EXAMPLE 5
```
PS C:\>Get-DhcpServerv6OptionValue -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020:: -OptionId 23
```

This example gets the DHCPv6 option value configured on the specified scope for the specified option identifier.

### EXAMPLE 6
```
PS C:\>Get-DhcpServerv6OptionValue -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020:: -All
```

This example gets all of the DHCPv6 option values configured on the specified scope.
The DHCPv6 option values that are returned include the standard as well as vendor class or user class specific options.

### EXAMPLE 7
```
PS C:\>Get-DhcpServerv6OptionValue -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020:: -Brief
```

This example gets all of the standard DHCPv6 option values configured on the specified scope.
The object that is returned does not contain the name of the option.
The **Brief** parameter improves the performance of this cmdlet by not requesting the name of the option from the DHCP server service.

### EXAMPLE 8
```
PS C:\>Get-DhcpServerv6OptionValue -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020:: -UserClass LabComputer
```

This example gets all of the user class specific DHCPv6 option values configured on the specified scope for the specified user class.

## PARAMETERS

### -All
Gets the option values for a scope, server, or reservation.
Option values can include vendor class and user class specific. 

If only this parameter is specified, then this cmdlet will get all of the option values for the specified scope, reservation, or server. 

If the **OptionId** parameter and this parameter are specified, then option values for the specified option ID for all of the vendor classes and user classes will be returned. 

If the **VendorClass** parameter and this parameter are specified, then all of the option values for the specified vendor class including those for any user class would be returned. 

If the **UserClass** parameter and this parameter are specified, then all of the option values for the specified user class including any vendor specific options would be returned.

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

### -Brief
Specifies that the name of the option is not returned in the option value object.
This parameter improves the performance of this cmdlet by not requesting the name of the option from the Dynamic Host Configuration Protocol (DHCP) server service.
For repeatedly fetching a large number of option values with this cmdlet, use of this parameter is recommended.

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

### -OptionId
Specifies the numerical identifier of the options for which one or more values are being requested.
If this parameter is not specified, then all option values configured are returned.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Prefix
Specifies the IPv6 subnet prefix of the scope for which the option values are being requested.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReservedIP
Specifies the reserved IPv6 address for which the option values are being requested.

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
Specifies that the option values for the specified user class are returned.

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

### -VendorClass
Specifies that the option values for the specified vendor class are returned.

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

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4OptionDefinition
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Policy
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Reservation
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6OptionValue[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Remove-DhcpServerv6OptionValue](./Remove-DhcpServerv6OptionValue.md)

[Set-DhcpServerv6OptionValue](./Set-DhcpServerv6OptionValue.md)

