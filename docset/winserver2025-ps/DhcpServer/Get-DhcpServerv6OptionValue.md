---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerV6OptionValue_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv6optionvalue?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DhcpServerv6OptionValue
---

# Get-DhcpServerv6OptionValue

## SYNOPSIS
Returns the IPv6 option values for one or more IPv6 options either for a specific reserved IP, scope or, server level.

## SYNTAX

```
Get-DhcpServerv6OptionValue [-ComputerName <String>] [-VendorClass <String>] [[-Prefix] <IPAddress>]
 [-ReservedIP <IPAddress>] [-UserClass <String>] [[-OptionId] <UInt32[]>] [-All] [-Brief]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DhcpServerv6OptionValue** cmdlet returns the IPv6 option values for one or more IPv6 options either for a specific reserved IP, scope, or server level.
The option identifier (ID) can be a standard option or for a specified vendor class.
If you do not specify the *OptionId* parameter, all option values at the requested level, such as reservation, scope, server, are returned.

If you specify the *ReservedIP* parameter, the option values set at the reservation level are returned.
If you specify the *Prefix* parameter, the option values set at the specified scope level are returned.
If you specify neither the *Prefix* nor the *ReservedIP* parameter, the option values set at the server level are returned.

If you specify neither the *VendorClass* nor the *UserClass* parameter, this cmdlet returns the standard option values.

## EXAMPLES

### Example 1: Get standard option values at the server level
```
PS C:\> Get-DhcpServerv6OptionValue -ComputerName "dhcpserver.contoso.com"
```

This example gets all of the standard DHCPv6 option values, non-class specific, configured at the server level.

### Example 2: Get standard option values for a scope
```
PS C:\> Get-DhcpServerv6OptionValue -ComputerName "dhcpserver.contoso.com" -Prefix 2001:4898:7020:1020::
```

This example gets all of the standard DHCPv6 option values, non-class specific, configured for the specified scope.

### Example 3: Get standard options values for a reservation
```
PS C:\> Get-DhcpServerv6OptionValue -ComputerName "dhcpserver.contoso.com" -ReservedIP 2001:4898:7020:1020::5
```

This example gets all of the standard DHCPv6 option values, non-class specific, configured for the specified reservation.

### Example 4: Get verdor class specific option values for a vendor class
```
PS C:\> Get-DhcpServerv6OptionValue -ComputerName "dhcpserver.contoso.com" -Prefix 2001:4898:7020:1020:: -VendorClass "MSUCClient"
```

This example gets all of the vendor class specific DHCPv6 option values configured on the specified scope for the specified vendor class.

### Example 5: Get an option value for a scope by using option ID
```
PS C:\> Get-DhcpServerv6OptionValue -ComputerName "dhcpserver.contoso.com" -Prefix 2001:4898:7020:1020:: -OptionId 23
```

This example gets the DHCPv6 option value configured on the specified scope for the specified option identifier.

### Example 6: Get all option values for a scope
```
PS C:\> Get-DhcpServerv6OptionValue -ComputerName "dhcpserver.contoso.com" -Prefix 2001:4898:7020:1020:: -All
```

This example gets all of the DHCPv6 option values configured on the specified scope.
The DHCPv6 option values that are returned include the standard and also vendor class or user class specific options.

### Example 7: Get standard option values for a scope in brief
```
PS C:\> Get-DhcpServerv6OptionValue -ComputerName "dhcpserver.contoso.com" -Prefix 2001:4898:7020:1020:: -Brief
```

This example gets all of the standard DHCPv6 option values configured on the specified scope.
The object that is returned does not contain the name of the option.
The *Brief* parameter improves the performance of this cmdlet by not requesting the name of the option from the DHCP server service.

### Example 8: Get user specific option values for a user class
```
PS C:\> Get-DhcpServerv6OptionValue -ComputerName "dhcpserver.contoso.com" -Prefix 2001:4898:7020:1020:: -UserClass "LabComputer"
```

This example gets all of the user class specific DHCPv6 option values configured on the specified scope for the specified user class.

## PARAMETERS

### -All
Indicates that this cmdlet gets the option values for a scope, server, or reservation.
Option values can include vendor class and user class specific.

If only this parameter is specified, this cmdlet gets all of the option values for the specified scope, reservation, or server.

If you specify the *OptionId* parameter and this parameter, option values for the specified option ID for all of the vendor classes and user classes are returned.

If you specify the *VendorClass* parameter and this parameter, all of the option values for the specified vendor class including those for any user class would be returned.

If you specify the *UserClass* parameter and this parameter, all of the option values for the specified user class including any vendor specific options would be returned.

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

### -Brief
Specifies that the name of the option is not returned in the option value object.
This parameter improves the performance of this cmdlet by not requesting the name of the option from the Dynamic Host Configuration Protocol (DHCP) server service.
For repeatedly fetching a large number of option values by using this cmdlet, we recommend use of the *Brief* parameter.

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

### -OptionId
Specifies the numeric identifier of the options for which one or more values are being requested.
If you do not specify this parameter, all option values configured are returned.

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
Specifies the IPv6 subnet prefix of the scope for which the option values are requested.

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
Specifies the reserved IPv6 address for which the option values are requested.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

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

