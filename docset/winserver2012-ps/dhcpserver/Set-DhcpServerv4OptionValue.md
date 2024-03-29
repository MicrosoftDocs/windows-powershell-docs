---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://learn.microsoft.com/powershell/module/dhcpserver/set-dhcpserverv4optionvalue?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DhcpServerv4OptionValue

## SYNOPSIS
Sets an IPv4 option value at the server, scope, or reservation level.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-DhcpServerv4OptionValue [-OptionId] <UInt32> [-Value] <String[]> [[-ScopeId] <IPAddress>] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-Force] [-PassThru] [-PolicyName <String>]
 [-ReservedIP <IPAddress>] [-ThrottleLimit <Int32>] [-UserClass <String>] [-VendorClass <String>] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-DhcpServerv4OptionValue [[-ScopeId] <IPAddress>] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-DnsDomain <String>] [-DnsServer <IPAddress[]>] [-Force] [-PassThru]
 [-PolicyName <String>] [-ReservedIP <IPAddress>] [-Router <IPAddress[]>] [-ThrottleLimit <Int32>]
 [-UserClass <String>] [-WinsServer <IPAddress[]>] [-Wpad <String>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-DhcpServerv4OptionValue** cmdlet sets an IPv4 option value at the server, scope, or reservation level.
The definition for the option must already exist.
This cmdlet will fail if the option definition does not exist in the Dynamic Host Configuration Protocol (DHCP) server service.
If only the **ReservedIP** parameter is specified, then the option values are set at the reservation level.
If only the **ScopeId** parameter is specified, then the option values are set at the scope level.
If neither the **ScopeId** nor **ReservedIP** parameter is specified, then the option values are set at the server level.
If the **VendorClass** parameter is specified, then the option value is set for that vendor class.
If the **UserClass** parameter is specified, then the option value is set for that user class.
If the **PolicyName** parameter is specified, then the option values are set for that policy.
The **UserClass** and **PolicyName** parameters cannot both be specified.
The **ScopeId** and **ReservedIP** parameters cannot both be specified.

The **PolicyName** and **ReservedIP** parameters cannot both be specified.

Note: The option values for policies can only be set for a DHCP server service running on Windows Server® 2012.
Setting user class options for a DHCP server service running on Windows Server 2012 creates of a policy with the policy name set to the name of the user class.
For a DHCP server service running on firstref_server_7 or earlier, only option values based upon the user class can be set.

To set options based upon legacy user classes, then the **UserClass** parameter must be specified.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -DnsServer 192.168.1.2 -WinsServer 192.168.1.3 -DnsDomain contoso.com -Router 192.168.1.1 -Wpad http://proxy.contoso.com/wpad.dat
```

This example sets the server level option values for DNS server, WINS server, DNS domain, router, and WPAD.

### EXAMPLE 2
```
PS C:\>Set-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -DnsServer 192.168.1.2 -WinsServer 192.168.1.3 -DnsDomain contoso.com -Router 192.168.1.1 -Wpad http://proxy.contoso.com/wpad.dat
```

This example sets the option values for DNS server, WINS server, DNS domain, router, and WPAD for scope 10.10.10.0.

### EXAMPLE 3
```
PS C:\>Set-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ReservedIP 10.10.10.5 -DnsServer 192.168.1.2 -WinsServer 192.168.1.3 -DnsDomain contoso.com -Router 192.168.1.1 -Wpad http://proxy.contoso.com/wpad.dat
```

This example sets the option values for DNS server, WINS server, DNS domain, router, and WPAD for reserved IP address 10.10.10.5.

### EXAMPLE 4
```
PS C:\>Set-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -PolicyName LabComputers -DnsServer 192.168.1.2 -WinsServer 192.168.1.3 -DnsDomain contoso.com -Router 192.168.1.1 -Wpad http://proxy.contoso.com/wpad.dat
```

This example sets the option values for DNS server, WINS server, DNS domain, router, and WPAD for policy named LabComputers in the scope 10.10.10.0.

### EXAMPLE 5
```
PS C:\>Set-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -OptionId 6 -Value 192.168.1.1
```

This example sets the server-wide DHCPv4 option value for option ID 6, or DNS server.

### EXAMPLE 6
```
PS C:\>Set-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -OptionId 6 -Value 192.168.1.1
```

This example sets the DHCPv4 option value for option ID 6, or DNS server, for the scope 10.10.10.0.

### EXAMPLE 7
```
PS C:\>Set-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ReservedIP 10.10.10.5 -OptionId 6 -Value 192.168.1.1
```

This example sets the DHCPv4 option value for option ID 6, or DNS server, for the specified reservation.

### EXAMPLE 8
```
PS C:\>Set-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -VendorClass MSUCClient -OptionId 5 -Value 6874747073
```

This example sets the vendor-class-specific DHCPv4 option value for option ID 5 on the specified scope for the specified vendor class named MSUCClient.

### EXAMPLE 9
```
PS C:\>Set-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -PolicyName PrinterPolicy -OptionId 6 -Value 192.168.1.10
```

This example sets the DHCPv4 option value for option ID 6, or DNS server, on the specified scope for the specified policy.

### EXAMPLE 10
```
PS C:\>Set-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -UserClass LabComputer -OptionId 6 -Value 192.168.1.10
```

This example sets the user-class-specific DHCPv4 option value for option ID 6, or DNS server, on the specified scope for the specified user class.

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

### -DnsDomain
Specifies the value for the DNS domain option.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DnsServer
Specifies one or more values for the DNS server option, in the IPv4 address format.

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

### -Force
Specifies that the DNS server validation will be skipped.
This parameter is only applicable if the **DnsServer** parameter is specified.

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

### -OptionId
Specifies the numeric identifier (ID) of the option for which one or more values are set.

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

### -PolicyName
Specifies the name of the policy for which one or more option values are set.

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

### -ReservedIP
Specifies the IPv4 address of the reservation for which one or more option values are set.

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

### -Router
Specifies one or more values for the router or default gateway option, in IPv4 address format.

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

### -ScopeId
Specifies the scope ID, in IPv4 address format for which one or more option values are set.

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
Sets the option value for the specified user class.

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
Specifies one or more values to be set for the option.
The format that the values need to be specified is specified per the data type of the options as follows: 

 -- Byte, Word, DWord, DWordDword: The values need to be specified as decimal or hexadecimal strings 

 -- IPAddress, IPv6Address: The values will need to be specified as strings 

 -- String: The values will need to be specified as strings 

 -- BinaryData, EncapsulatedData: The values will need to be specified as hexadecimal strings

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
Sets the option value for the specified vendor class.

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

### -WinsServer
Specifies the values for the WINS server option, in IPv4 address format.

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

### -Wpad
Specifies the value for the web proxy auto detection option.
The value for this option is specified as a URL.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4OptionDefinition
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4OptionValue
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4OptionValue
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DhcpServerv4OptionValue](./Get-DhcpServerv4OptionValue.md)

[Remove-DhcpServerv4OptionValue](./Remove-DhcpServerv4OptionValue.md)

