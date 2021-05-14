---
external help file: PS_DhcpServerV6OptionValue_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/dhcpserver/remove-dhcpserverv6optionvalue?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DhcpServerv6OptionValue
---

# Remove-DhcpServerv6OptionValue

## SYNOPSIS
Deletes one or more DHCPv6 option values set at the reservation level, scope level, or server level, either for the standard IPv6 options or for a specified vendor class.

## SYNTAX

```
Remove-DhcpServerv6OptionValue [-ComputerName <String>] [[-Prefix] <IPAddress>] [-ReservedIP <IPAddress>]
 [-OptionId] <UInt32[]> [-PassThru] [-VendorClass <String>] [-UserClass <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DhcpServerv6OptionValue** cmdlet deletes one or more DHCPv6 option values set at the reservation level, scope level, or server level, either for the standard IPv6 options or for a specified vendor class.

If only the **ReservedIP** parameter is specified, then the option values set at the reservation level are deleted.
If only the **Prefix** parameter is specified, then the option values set at the specified IPv6 scope are deleted.
If neither the **ScopeId** nor **ReservedIP** parameter is specified, then the option values set at the server level are deleted.
The **ScopeId** and **ReservedIP** parameters cannot both be specified.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-DhcpServerv6OptionValue -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020:: -OptionId 23
```

This cmdlet deletes the DHCPv6 option value configured on the specified scope for the specified option ID.

### EXAMPLE 2
```
PS C:\>Remove-DhcpServerv6OptionValue -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020:: -VendorClass MyVendorClass -OptionId 10
```

This cmdlet deletes the specified vendor class specific option from the specified prefix.

### EXAMPLE 3
```
PS C:\>Remove-DhcpServerv6OptionValue -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020:: -OptionId 23
```

This cmdlet deletes the DHCPv6 option value configured on the specified scope for the specified option identifier.

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
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the Dynamic Host Configuration Protocol (DHCP) server service.

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

### -OptionId
Specifies one or more numeric identifiers (IDs) for the options being deleted.

```yaml
Type: UInt32[]
Parameter Sets: (All)
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
Specifies the IPv6 subnet prefix of the scope from which one or more option values are deleted.

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
Specifies the IPv6 address of the reservation from which one or more option values are deleted.

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
Specifies that only the option values for the specified user class is deleted.

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
Specifies that only the option values for the specified vendor class is deleted.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6OptionDefinition
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6OptionValue
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6OptionValue[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DhcpServerv6OptionValue](./Get-DhcpServerv6OptionValue.md)

[Set-DhcpServerv6OptionValue](./Set-DhcpServerv6OptionValue.md)

