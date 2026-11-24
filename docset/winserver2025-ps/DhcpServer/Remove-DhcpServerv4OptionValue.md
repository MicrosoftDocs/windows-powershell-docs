---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerV4OptionValue_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/remove-dhcpserverv4optionvalue?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DhcpServerv4OptionValue
---

# Remove-DhcpServerv4OptionValue

## SYNOPSIS
Deletes one or more IPv4 option values at the server, scope or reservation level, either for the standard IPv4 options or for the specified vendor or user class.

## SYNTAX

```
Remove-DhcpServerv4OptionValue [-VendorClass <String>] [-ComputerName <String>] [-OptionId] <UInt32[]>
 [-UserClass <String>] [[-ScopeId] <IPAddress>] [-ReservedIP <IPAddress>] [-PassThru] [-PolicyName <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DhcpServerv4OptionValue** cmdlet deletes one or more IPv4 option values at the server, scope or reservation level, either for the standard IPv4 options or for the specified vendor or user class.

If you specify only the *ReservedIP* parameter, the option values set at the reservation level are deleted.
If you specify only the *ScopeId* parameter, the option values set at the scope level are deleted.
If you specify neither the *ScopeId* nor the *ReservedIP* parameter, the option values set at the server level are deleted.
The *ScopeId* and the *ReservedIP* parameters cannot both be specified.

The *UserClass* and *PolicyName* parameters cannot both be specified.

## EXAMPLES

### Example 1: Delete an option value on a scope
```
PS C:\> Remove-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -OptionId 23
```

This example deletes DHCPv4 option value configured on the specified scope for the specified option ID.

### Example 2: Delete an option value for a vendor class
```
PS C:\> Remove-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -VendorClass "MSUCClient" -OptionId 5
```

This example deletes DHCPv4 option value configured on the specified scope for the specified vendor class named MSUCClient with the specific option 5.

### Example 3: Delete an option value by using an option ID
```
PS C:\> Remove-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -PolicyName "SmartPhonePolicy" -OptionId 252
```

This example deletes DHCPv4 option value with the option ID 252 configured for the specified policy in the scope 10.10.10.0.

### Example 4: Delete an option value for a user class in a scope
```
PS C:\> Remove-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -UserClass "LabComputer" -OptionId 252
```

This example deletes DHCPv4 option value with the option ID 252 configured for the specified user class in the scope 10.10.10.0.

### Example 5: Delete an option value at the server level
```
PS C:\> Remove-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -OptionId 23
```

This example deletes DHCPv4 option value configured at the server level, or server-wide, for the specified option ID.

### Example 6: Delete an otion value at the server level for a vendor class
```
PS C:\> Remove-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -VendorClass "MSUCClient" -OptionId 5
```

This example deletes DHCPv4 option value configured at the server level, or server-wide, for the specified vendor class named MSUCClient with the specific option 5.

### Example 7: Delete an option value at the server level by using an option ID
```
PS C:\> Remove-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -PolicyName "SmartPhonePolicy" -OptionId 252
```

This example deletes DHCPv4 option value with the option ID 252 configured for the specified policy at the server level, or server-wide.

### Example 8: Delete an option value by using an option ID for a user class
```
PS C:\> Remove-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -UserClass "LabComputer" -OptionId 252
```

This example deletes DHCPv4 option value with the option ID 252 configured for the specified user class at the server level, or server-wide.

### Example 9: Delete an option value on a reservation
```
PS C:\> Remove-DhcpServerv4OptionValue -ComputerName "dhcpserver.contoso.com" -ReservedIP 10.10.10.5 -OptionId 23
```

This example deletes DHCPv4 option value configured on the specified reservation for the specified option ID.

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

### -OptionId
Specifies one or more numeric identifiers (IDs) for the options which are to be deleted.

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

### -PolicyName
Specifies the name of the policy from which the option values are deleted.

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
Specifies the IPv4 address of the reservation from which the option values are deleted.

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

### -ScopeId
Specifies the scope ID, in IPv4 address format, from which the option values are deleted.

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
Specifies that the option values for the specified user class are deleted.

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
Specifies that the option values for the specified vendor class are deleted.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4OptionValue
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4OptionValue[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DhcpServerv4OptionValue](./Get-DhcpServerv4OptionValue.md)

[Set-DhcpServerv4OptionValue](./Set-DhcpServerv4OptionValue.md)

