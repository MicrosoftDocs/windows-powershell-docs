---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerv4Policy_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/set-dhcpserverv4policy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DhcpServerv4Policy
---

# Set-DhcpServerv4Policy

## SYNOPSIS
Sets the properties of a policy at the server level or at the specified scope level.

## SYNTAX

```
Set-DhcpServerv4Policy [-ComputerName <String>] [-Description <String>] [-Name] <String>
 [[-ScopeId] <IPAddress>] [-Enabled <Boolean>] [-MacAddress <String[]>] [-Fqdn <String[]>]
 [-UserClass <String[]>] [-SubscriberId <String[]>] [-NewName <String>] [-ClientId <String[]>] [-PassThru]
 [-LeaseDuration <TimeSpan>] [-ProcessingOrder <UInt16>] [-RelayAgent <String[]>] [-RemoteId <String[]>]
 [-CircuitId <String[]>] [-Condition <String>] [-VendorClass <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DhcpServerv4Policy** cmdlet sets the properties of an existing policy either at the server level or at the specified scope level.
If the *CircuitId*, *ClientId*, *Fqdn*, *MACAddress*, *RelayAgent*, *RemoteId*, *SubscriberId*, *UserClass*, or *VendorClass* parameter is specified, the conditions of the policy are being changed and this cmdlet behaves as follows:

If the *VendorClass* parameter is specified and the policy being modified already has conditions for the *VendorClass* parameter value, the existing *VendorClass* parameter value is removed and the new *VendorClass* parameter value is added.

However, if the policy being modified has conditions for the *MacAddress* parameter value, the *MacAddress* parameter value is not changed and is logically combined (ORꞌd) or differenced (ANDꞌd) with the *VendorClass*-based conditions.

The same applies to any of the *CircuitId*, *ClientId*, *Fqdn*, *MACAddress*, *RelayAgent*, *RemoteId*, *SubscriberId*, *UserClass*, or *VendorClass* parameters that are used in the conditions.

## EXAMPLES

### Example 1: Modify a server level policy
```
PS C:\> Set-DhcpServerv4Policy -ComputerName "dhcpserver.contoso.com" -Name "DevicesPolicy" -NewName TabletPolicy -Description "policy for tablet devices" -ProcessingOrder 4 -Enabled $False
```

This example renames the server level policy named DevicesPolicy to TabletPolicy, sets a description string, disables the policy, and sets the processing order to 4.

### Example 2: Modify the conditions of the server level policy
```
PS C:\> Set-DhcpServerv4Policy -Name "PhysicalMachinesPolicy" -Condition OR -MacAddress NE,00155D*,000569*
```

This example modifies the conditions of the server level policy for non-Hyper-V clients.
If the policy had an existing MAC address based condition, the same condition is replaced with the condition specified in this cmdlet.
However, if the policy had conditions based on other fields, such as the *VendorClass*, *UserClass*, *ClientId*, or *RelayAgent* parameters, those is retained and logically combined (ORꞌd) with the newly added MAC address based condition.

### Example 3: Modify the conditions of the server level policy for non-Hyper-V clients
```
PS C:\> Set-DhcpServerv4Policy -Name "PhysicalMachinesPolicy" -Condition OR -MacAddress NE,00155D*,000569* -VendorClass ""
```

This example modifies the conditions of the server level policy for non-Hyper-V clients.
If the policy had an existing MAC address based condition, a vendor class based policy, or both, the conditions are replaced with the condition specified in this cmdlet.

### Example 4: Sets lease duration for a server level policy
```
PS C:\> Set-DhcpServerv4Policy -Name "TabletPolicy" -ComputerName "dhcpserver.contoso.com" -LeaseDuration 10
```

This example sets the lease duration for the server level policy named TabletPolicy to 10 days for the specified computer.

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

### -CircuitId
Specifies the comparator to use and the values with which to compare the circuit identifier (ID) sub-option.
The first element is the comparator, EQ or NE, followed by a single value.
If the last character in a value is an asterisk, the subsequent characters are treated as wildcard characters for the comparison.
If the first character in a value-element is an asterisk, the preceding characters are treated as wildcard characters for comparison.

The value can be followed by another comparator, EQ or NE, which is followed by another value.

The input format for the value is a hexadecimal string with or without hyphen separation.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientId
Specifies the comparator to use and the values with which to compare the client identifier.
The first element is the comparator, EQ or NE, followed by a set of values.
If the last character in a value is an asterisk, the subsequent characters are treated as wildcard characters for the comparison.
If the first character in a value-element is an asterisk, the preceding characters are treated as wildcard characters for comparison.

The values can be followed by another comparator, EQ or NE, which is followed by another set of values.

The input format is a hexadecimal string with or without hyphen separation.
The output format is a hexadecimal string with hyphen separation.

The values following the EQ operator is treated as multiple assertions which are logically combined (ORꞌd).

The values following the NE operator is treated as multiple assertions which are logically differenced (ANDꞌd).

An example of the format is: `EQ, 00-11-22-33-44-55, AA-BB-CC-DD-EE*`.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Condition
Specifies the logical operator between the conditions when multiple conditions are specified.
The acceptable values for this parameter are: AND or OR.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: And, Or

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
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies the description to set on the policy.

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

### -Enabled
Specifies the enabled state for the policy.

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

### -Fqdn
Specifies the comparator to use and the values with which to compare the fully qualified domain name (FQDN) in the client request.
The first element is the comparator, EQ, NE, Isl, or Insl and the subsequent elements are values.
For the comparators Island Insl, use a blank value.
If the last character in a value is an asterisk, the subsequent characters are treated as wildcard characters for the comparison.
If the first character in a value-element is an asterisk, the preceding characters are treated as wildcard characters for comparison.

The values can again be followed by another comparator, EQ or NE, which is followed by another set of values.

The input format is a string.
A trailing wildcard character can be present to indicate partial match.

The values following the EQ operator are treated as multiple assertions which are logically combined (OR'd).

The values following the NE operator are treated as multiple assertions which are logically differenced (AND'd).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LeaseDuration
Specifies the duration of the lease for clients that match the policy.

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

### -MacAddress
Specifies the comparator to use and the values with which to compare the MAC Address in the client request.
The first element is the comparator, EQ or NE, followed by a set of values.
If the last character in a value is an asterisk, the subsequent characters are treated as wildcard characters for the comparison.
If the first character in a value-element is an asterisk, the preceding characters are treated as wildcard characters for comparison.

The values can be followed by another comparator, EQ or NE, which is followed by another set of values.

The input format is a hexadecimal string with or without hyphen separation.
A trailing wildcard character can be used to indicate partial match.
The output format is a hexadecimal string with hyphen separation.

The values following the EQ operator is treated as multiple assertions which are logically combined (ORꞌd).

The values following the NE operator is treated as multiple assertions which are logically differenced (ANDꞌd).

An example of the format is: `00-1F-3B-7C-B7-89, 00-1F-3B-7C-B7-*, 001F3B7CB789`.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the policy being modified.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewName
Specifies the new name to set for the policy.

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

### -ProcessingOrder
Specifies the order for this policy with regard to other policies in the scope or DHCP server service.
The DHCP server service processes the policies in the specified order while evaluating client requests using the configured policies.

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

### -RelayAgent
Specifies the comparator to use and the values with which to compare the relay agent information.
The first element is the comparator, EQ or NE, followed by a set of values.
If the last character in a value is an asterisk, the subsequent characters are treated as wildcard characters for the comparison.
If the first character in a value-element is an asterisk, the preceding characters are treated as wildcard characters for comparison.

The values can be followed by another comparator, EQ or NE, which is followed by another set of values.

The input format is a hexadecimal string with or without hyphen separation.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RemoteId
Specifies the comparator to use and the values with which to compare the remote ID suboption.
The first element is the comparator, EQ or NE, followed by a single value.
If the last character in a value is an asterisk, the subsequent characters are treated as wildcard characters for the comparison.
If the first character in a value-element is an asterisk, the preceding characters are treated as wildcard characters for comparison.

The value can again be followed by another comparator, EQ or NE, which is followed by another value.

The input format for the value is a hexadecimal string with or without hyphen separation.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScopeId
Specifies the scope ID, in IPv4 address format, of the scope which contains the policy.
If this parameter is not specified, the server level policy is modified.

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

### -SubscriberId
Specifies the comparator to use and the values with which to compare the subscriber ID suboption.
The first element is the comparator, EQ or NE, and followed by a single value.
If the last character in a value is an asterisk, the subsequent characters are treated as wildcard characters for the comparison.
If the first character in a value-element is an asterisk, the preceding characters are treated as wildcard characters for comparison.

The value can again be followed by another comparator, EQ or NE, which is followed by another value.

The input format is a hexadecimal string with or without hyphen separation.

```yaml
Type: String[]
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
Specifies the comparator to use and the user class values with which to compare the user class field in the client request.
The first element to be specified is the comparator, EQ or NE, and followed by a set values.
If the last character in a value is an asterisk, the subsequent characters are treated as wildcard characters for the comparison.
If the first character in a value-element is an asterisk, the preceding characters are treated as wildcard characters for comparison.

The values can be followed by another comparator, EQ or NE, which is followed by another set of values.

The values to be specified must be the user class names that already exist on the DHCP server service.

The format of the value should be a hexadecimal string starting with `0x`.

The values following the EQ operator are treated as multiple assertions which are logically combined (ORꞌd).

The values following the NE operator are treated as multiple assertions which are logically differenced (ANDꞌd).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VendorClass
Specifies the comparator to use and the vendor class values with which to compare the vendor class field in the client request.
The first element is the comparator, EQ or NE, followed by a set of values.
If the last character in a value is an asterisk, the subsequent characters are treated as wildcard characters for the comparison.
If the first character in a value-element is an asterisk, the preceding characters are treated as wildcard characters for comparison.

The values can be followed by another comparator.
EQ or NE, which is followed by another set of values.

The values to be specified must be the vendor class names that already exist on the DHCP server service.

The format of the value should be a hexadecimal string starting with `0x`.

The values following the EQ operator are treated as multiple assertions which are logically combined (ORꞌd).

The values following the NE operator are treated as multiple assertions which are logically differenced (ANDꞌd).

```yaml
Type: String[]
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Policy
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Policy
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4Policy](./Add-DhcpServerv4Policy.md)

[Add-DhcpServerv4PolicyIPRange](./Add-DhcpServerv4PolicyIPRange.md)

[Get-DhcpServerv4Policy](./Get-DhcpServerv4Policy.md)

[Get-DhcpServerv4PolicyIPRange](./Get-DhcpServerv4PolicyIPRange.md)

[Remove-DhcpServerv4Policy](./Remove-DhcpServerv4Policy.md)

[Remove-DhcpServerv4PolicyIPRange](./Remove-DhcpServerv4PolicyIPRange.md)

