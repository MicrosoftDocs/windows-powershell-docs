---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerV4OptionValue_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/set-dhcpserverv4optionvalue?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DhcpServerv4OptionValue
---

# Set-DhcpServerv4OptionValue

## SYNOPSIS
Sets an IPv4 option value at the server, scope, or reservation level.

## SYNTAX

### OptionIds (Default)
```
Set-DhcpServerv4OptionValue [-PolicyName <String>] [-PassThru] [-Force] [-ReservedIP <IPAddress>]
 [[-ScopeId] <IPAddress>] [-UserClass <String>] [-ComputerName <String>] [-VendorClass <String>]
 [-Value] <String[]> [-OptionId] <UInt32> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CommonOptions
```
Set-DhcpServerv4OptionValue [-PolicyName <String>] [-PassThru] [-Force] [-DnsDomain <String>]
 [-DnsServer <IPAddress[]>] [-ReservedIP <IPAddress>] [-Router <IPAddress[]>] [[-ScopeId] <IPAddress>]
 [-UserClass <String>] [-WinsServer <IPAddress[]>] [-Wpad <String>] [-ComputerName <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DhcpServerv4OptionValue** cmdlet sets an IPv4 option value at the server, scope, or reservation level.
The definition for the option must already exist.
This cmdlet fails if the option definition does not occur in the Dynamic Host Configuration Protocol (DHCP) server service.

If you specify only the *ReservedIP* parameter, the option values are set at the reservation level.
If you specify only the *ScopeId* parameter, the option values are set at the scope level.

If you specify neither the *ScopeId* nor *ReservedIP* parameter, the option values are set at the server level.
If you specify the *VendorClass* parameter, the option value is set for that vendor class.

If you specify the *UserClass* parameter, the option value is set for that user class.

If you specify the *PolicyName* parameter, the option values are set for that policy.
The *UserClass* and *PolicyName* parameters cannot both be specified.
The *ScopeId* and *ReservedIP* parameters cannot both be specified.

The *PolicyName* and *ReservedIP* parameters cannot both be specified.

The option values for policies can only be set for a DHCP server service that runs on Windows Server® 2012 and later versions of the Windows operating system.
Setting user class options for a DHCP server service that runs on Windows Server 2012 and later versions of the Windows operating creates of a policy with the policy name set to the name of the user class.
For a DHCP server service that runs on firstref_server_7 or earlier, only option values based on the user class can be set.

To set options based on legacy user classes, the *UserClass* parameter must be specified.

## EXAMPLES

### Example 1: Set server level option values
```
PS C:\> Set-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -DnsServer 192.168.1.2 -WinsServer 192.168.1.3 -DnsDomain "contoso.com" -Router 192.168.1.1 -Wpad "http://proxy.contoso.com/wpad.dat"
```

This example sets the server level option values for DNS server, WINS server, DNS domain, router, and WPAD.

### Example 2: Set option values for a scope
```
PS C:\> Set-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -DnsServer 192.168.1.2 -WinsServer 192.168.1.3 -DnsDomain "contoso.com" -Router 192.168.1.1 -Wpad "http://proxy.contoso.com/wpad.dat"
```

This example sets the option values for DNS server, WINS server, DNS domain, router, and WPAD for scope 10.10.10.0.

### Example 3: Set option values for an address
```
PS C:\> Set-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -ReservedIP 10.10.10.5 -DnsServer 192.168.1.2 -WinsServer 192.168.1.3 -DnsDomain "contoso.com" -Router 192.168.1.1 -Wpad "http://proxy.contoso.com/wpad.dat"
```

This example sets the option values for DNS server, WINS server, DNS domain, router, and WPAD for reserved IP address 10.10.10.5.

### Example 4: Set option values for a policy
```
PS C:\> Set-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -PolicyName "LabComputers" -DnsServer 192.168.1.2 -WinsServer 192.168.1.3 -DnsDomain "contoso.com" -Router 192.168.1.1 -Wpad "http://proxy.contoso.com/wpad.dat"
```

This example sets the option values for DNS server, WINS server, DNS domain, router, and WPAD for policy named LabComputers in the scope 10.10.10.0.

### Example 5: Set service-wide option value for DNS server
```
PS C:\> Set-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -OptionId 6 -Value "192.168.1.1"
```

This example sets the server-wide DHCPv4 option value for option ID 6, or DNS server.

### Example 6: Set option value for DNS server for a scope
```
PS C:\> Set-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -OptionId 6 -Value "192.168.1.1"
```

This example sets the DHCPv4 option value for option ID 6, or DNS server, for the scope 10.10.10.0.

### Example 7: Set option value for DNS server for a reservation
```
PS C:\> Set-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -ReservedIP 10.10.10.5 -OptionId 6 -Value "192.168.1.1"
```

This example sets the DHCPv4 option value for option ID 6, or DNS server, for the specified reservation.

### Example 8: Set a vendor class specific option value
```
PS C:\> Set-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -VendorClass "MSUCClient" -OptionId 5 -Value ([System.Text.Encoding]::ASCII.GetBytes("/CertProv/CertProvisioningService.svc"))
```

This example sets the vendor class specific DHCPv4 option value for option ID 5 on the specified scope for the specified vendor class named MSUCClient.

### Example 9: Set option value for DNS server for a policy
```
PS C:\> Set-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -PolicyName "PrinterPolicy" -OptionId 6 -Value "192.168.1.10"
```

This example sets the DHCPv4 option value for option ID 6, or DNS server, on the specified scope for the specified policy.

### Example 10: Set a user class specific option value for DNS server
```
PS C:\> Set-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -UserClass "LabComputer" -OptionId 6 -Value "192.168.1.10"
```

This example sets the user class specific DHCPv4 option value for option ID 6, or DNS server, on the specified scope for the specified user class.

### Example 11: Set a vendor class specific option value for a scope
```
PS C:\> Set-DhcpServerv4OptionValue -ScopeId 10.10.10.0 -OptionId 43 -Value "241","08","33","255","132","10","33","255","133"
```

This example sets the vendor class specific DHCPv4 option value for option ID 43, or embedded vendor-specific options, on the specified scope.

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

### -DnsDomain
Specifies the value for the DNS domain option.

```yaml
Type: String
Parameter Sets: CommonOptions
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
This parameter is only applicable if the *DnsServer* parameter is specified.

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
Aliases: IPAddress

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
Parameter Sets: CommonOptions
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
Use the following formats:

- Byte, Word, DWord, DWordDword.
Specify as decimal or hexadecimal strings.
- IPAddress, IPv6Address.
Specify as strings.
- String.
Specify as strings.
- BinaryData, EncapsulatedData.
Specify as hexadecimal strings.

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
Sets the option value for the specified vendor class.

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

### -WinsServer
Specifies the values for the WINS server option, in IPv4 address format.

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

### -Wpad
Specifies the value for the web proxy auto detection option.
The value for this option is specified as a URL.

```yaml
Type: String
Parameter Sets: CommonOptions
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

