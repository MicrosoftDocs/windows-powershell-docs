---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerv4Policy_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/add-dhcpserverv4policy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DhcpServerv4Policy
---

# Add-DhcpServerv4Policy

## SYNOPSIS
Adds a new policy either at the server level or at the scope level.

## SYNTAX

```
Add-DhcpServerv4Policy [-ComputerName <String>] [-Name] <String> [-Condition] <String> [-Description <String>]
 [-ScopeId <IPAddress>] [-ProcessingOrder <UInt16>] [-RelayAgent <String[]>] [-RemoteId <String[]>]
 [-SubscriberId <String[]>] [-PassThru] [-LeaseDuration <TimeSpan>] [-Fqdn <String[]>] [-Enabled <Boolean>]
 [-VendorClass <String[]>] [-UserClass <String[]>] [-MacAddress <String[]>] [-CircuitId <String[]>]
 [-ClientId <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-DhcpServerv4Policy** cmdlet adds a new policy either at the server level or at the scope level.
The policy name must be unique at the level, either server or specific scope, where the policy is added and should have at least one condition as specified by the *CircuitId*, *ClientId*, *Fqdn*, *MACAddress*, *RelayAgent*, *RemoteId*, *SubscriberId*, *UserClass*, or *VendorClass* parameter.

## EXAMPLES

### Example 1: Create a server level policy for virtual machine clients
```
PS C:\> Add-DhcpServerv4Policy -Name "HyperVPolicy" -Condition OR -MacAddress EQ,00155D*,000569*
```

This example creates a server level policy for virtual machine clients.
The MAC addresses of Hyper-V virtual machines (00-15-5D) and VMWare virtual machines (00-05-69) are used as a condition in the policy.

### Example 2: Create a server level policy for non-virtual machine clients
```
PS C:\> Add-DhcpServerv4Policy -Name "PhysicalComputersPolicy" -Condition OR -MacAddress NE,00155D*,000569*
```

This example creates a server level policy for non-virtual machine clients.
The MAC address of Hyper-V virtual machines (00-15-5D) and VMware virtual machines (000569) is used as a negation condition in the policy.

### Example 3: Create a scope level policy for virtual machine clients
```
PS C:\> Add-DhcpServerv4Policy -Name "VMPolicy" -ScopeId 10.10.10.0 -Condition OR -MacAddress EQ,00155D*,000569*
```

This example creates a scope level policy for virtual machine clients inside the scope 10.10.10.0.
The MAC addresses of Hyper-V virtual machines (00-15-5D) and VMware virtual machines (00-05-69) are used as a condition in the policy.

### Example 4: Create a printer policy in a scope based on a vendor class
```
PS C:\> Add-DhcpServerv4Policy -Name "PrinterPolicy" -ScopeId 10.10.10.0 -Condition OR -VendorClass EQ,"HP Printer","Xerox Printer"
```

This example creates a printer policy inside the scope 10.10.10.0 based on the vendor class of printers.
The vendor classes must be defined before they are used in the policy.

### Example 5: Create a printer policy in a scope based on a user class
```
PS C:\> Add-DhcpServerv4Policy -Name "LabComputerPolicy" -ScopeId 10.10.10.0 -Condition OR -UserClass EQ,LabComputers
```

This example creates a lab computers policy inside the scope 10.10.10.0 based on the user class.
The user class must be defined before they are used in the policy.

### Example 6: Create a policy based on the relay agent information inside a scope
```
PS C:\> Add-DhcpServerv4Policy -Name "RelayAgentBasedPolicy" -ScopeId 10.10.10.0 -Condition OR -RelayAgent EQ,01030a0b0c02050000000123
```

This example creates a policy based on the relay agent information (option 82) inside the scope 10.10.10.0.
The DHCP relay agent must be configured to use the relay agent information option (option 82).

### Example 7: Create a policy by combining conditions based on a MAC address prefix and vendor class
```
PS C:\> Add-DhcpServerv4Policy -Name "DevicesPolicy" -ScopeId 10.10.10.0 -Condition OR -MacAddress EQ,F8DB7F* -VendorClass EQ,Android
```

This example creates a policy by combining conditions, using OR, based on MAC address prefix of HTC phone devices and vendor class of Android, inside the scope 10.10.10.0.
The vendor class must be defined before it is used in the policy.

### Example 8: Create a server level policy for virtual machine clients, assign a processing order
```
PS C:\> Add-DhcpServerv4Policy -Name "HyperVPolicy" -Condition OR -MacAddress EQ,00155D*,000569* -ProcessingOrder 2 -Enabled $False
```

This example creates a server level policy for virtual machine clients and assigns a processing order of 2 and creates the policy in a disabled state.
The MAC addresses of Hyper-V virtual machines (00-15-5D) and VMWare virtual machines (00-05-69) are used as a condition in the policy.

### Example 9: Create a policy by combining conditions based on a MAC address prefix and vendor class with lease duration
```
PS C:\> Add-DhcpServerv4Policy -Name "DevicesPolicy" -Condition OR -LeaseDuration 10 -MacAddress EQ,F8DB7F -ScopeId 10.10.10.0 -VendorClass "EQ","Android"
```

This example creates a policy by combining conditions, using OR, based on MAC address prefix of HTC phone devices and vendor class of Android, inside the scope 10.10.10.0.
The vendor class must be defined before it is used in the policy.
In addition, the command sets the lease duration for the clients to 10 days.

### Example 10: Create a server level policy for workgroup joined clients
```
PS C:\> Add-DhcpServerv4Policy -Name "WorkgroupDevices" -Condition OR -Fqdn "Isl"
```

This example creates a server level policy for workgroup joined clients.
The policy matches clients that have a single label FQDN in the conditions in the policy.

### Example 11: Create a server level policy for clients that are not members of a domain
```
PS C:\> Add-DhcpServerv4Policy -Name "ForeignDevices" -Condition OR -Fqdn NE,*.contoso.com
```

This example creates a server level policy for all foreign clients that are not members of the local domain contoso.com.
The policy matches clients that have an FQDN that does not contain the value contoso.com.

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
Specifies the comparator to use and the values with which to compare the circuit id sub-option.
The first element is the comparator, either EQ or NE, followed by a single value.

If the last character in a value is an asterisk, then the subsequent characters are treated as wildcard characters for the comparison.
If the first character in a value-element is an asterisk, the preceding characters are treated as wildcard characters for comparison.

The value can again be followed by another comparator, either EQ or NE, which is followed by another value for comparison.

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
Specifies the comparator to use and the values with which to compare client identifier.
The first element is the comparator, either EQ or NE, and subsequent elements are values.

If the last character in a value is an asterisk, then the subsequent characters are treated as wildcard characters for the comparison.
If the first character in a value-element is an asterisk, the preceding characters are treated as wildcard characters for comparison.

The values can again be followed by another comparator, either EQ or NE, which is followed by another set of values for comparison.

The input format is a hexadecimal string with or without hyphen separation.
For example: `EQ, 00-11-22-33-44-55, AA-BB-CC-DD-EE*`.

The output format is a hexadecimal string with hyphen separation.

The values that follow the EQ operator are treated as multiple assertions which are logically combined (OR'd).

The values that follow the NE operator are treated as multiple assertions which are logically differenced (AND'd).

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
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the DHCP server service.

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
Specifies the logical operator between conditions when multiple conditions are specified.
The acceptable values for this parameter are: AND and OR.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: And, Or

Required: True
Position: 2
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
Specifies the description string of the policy added.

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
Specifies the enabled state of a policy.

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
The first element is the comparator, EQ, NE, Isl, or Insl, and the subsequent elements are values.
For the comparators Island Insl, use a blank value.
If the last character in a value is an asterisk, then the subsequent characters are treated as wildcard characters for the comparison.
If the first character in a value-element is an asterisk, the preceding characters are treated as wildcard characters for comparison.

The values can again be followed by another comparator, EQ or NE, which is followed by another set of values.

The input format is a string.
A trailing wildcard character can be present to indicate partial match.

The values that follow the EQ operator are treated as multiple assertions which are logically combined (OR'd).

The values that follow the NE operator are treated as multiple assertions which are logically differenced (AND'd).

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
The first element is the comparator, EQ or NE, and the subsequent elements are values.
If the last character in a value is an asterisk, then the subsequent characters are treated as wildcard characters for the comparison.
If the first character in a value-element is an asterisk, the preceding characters are treated as for comparison.

The values can again be followed by another comparator, EQ or NE, which is followed by another set of values.

The input format is a hexadecimal string with or without hyphen separation.
A trailing wildcard character can be present to indicate partial match.
For example: `00-1F-3B-7C-B7-89, 00-1F-3B-7C-B7-*, 001F3B7CB789`.
The output format is a hexadecimal string with hyphen separation.

The values that follow the EQ operator are treated as multiple assertions which are logically combined (OR'd).

The values that follow the NE operator are treated as multiple assertions which are logically differenced (AND'd).

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
Specifies the name of the policy to be added.

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
Specifies the order of this policy with regard to other policies in the scope or server.
The DHCP server service processes the policies in the specified order when evaluating client requests.

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
Specifies the comparator to use and values with which to compare the relay agent information.
The first element is the comparator, EQ or NE, and subsequent elements are values.
If the last character in a value is an asterisk, then the subsequent characters are treated as wildcard characters for the comparison.
If the first character in a value-element is an asterisk, the preceding characters are treated as wildcard characters for comparison.

The values can again be followed by another comparator, EQ or NE, which is followed by another set of values.

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
Specifies the comparator to use and values with which to compare the remote ID sub-option.
The first element is the comparator, EQ or NE, followed by a single value.
If the last character in a value is an asterisk, then the subsequent characters are treated as wildcard characters for the comparison.
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
Specifies the scope identifier, in IPv4 address format, in which the policy is added.

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

### -SubscriberId
Specifies the comparator to use and the values with which to compare the subscriber ID sub-option.
The first element is the comparator, EQ or NE, and followed by a single value.
If the last character in a value is an asterisk, then the subsequent characters are treated as wildcard characters for the comparison.
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
Specifies the comparator to use and the user class values to compare with the user class field in the client request.
The first element to be specified is the comparator, EQ or NE, and the subsequent elements are values.
If the last character in a value is an asterisk, then the subsequent characters are treated as wildcard characters for the comparison.
If the first character in a value-element is an asterisk, the preceding characters are treated as wildcard characters for comparison.

The values can again be followed by another comparator, EQ or NE, which is followed by another set of values.

The values to be specified are the user class names which already exist on the server.

The values that follow the EQ operator are treated as multiple assertions which are logically combined (OR'd).

The values that follow the NE operator are treated as multiple assertions which are logically differenced (AND'd).

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
Specifies the comparator to use and vendor class values to compare with the vendor class field in the client request.
The first element is the comparator, EQ or NE, and the subsequent elements are values.
If the last character in a value is an asterisk, then the subsequent characters are treated as wildcard characters for the comparison.
If the first character in a value-element is an asterisk, the preceding characters are treated as wildcard characters for comparison.

The values can again be followed by another comparator, EQ or NE, which is followed by another set of values.

The values to be specified are the vendor class names which already exist on the server.

The values that follow the EQ operator are treated as multiple assertions which are logically combined (OR'd).

The values that follow the NE operator are treated as multiple assertions which are logically differenced (AND'd).

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

[Add-DhcpServerv4PolicyIPRange](./Add-DhcpServerv4PolicyIPRange.md)

[Get-DhcpServerv4Policy](./Get-DhcpServerv4Policy.md)

[Get-DhcpServerv4PolicyIPRange](./Get-DhcpServerv4PolicyIPRange.md)

[Remove-DhcpServerv4Policy](./Remove-DhcpServerv4Policy.md)

[Remove-DhcpServerv4PolicyIPRange](./Remove-DhcpServerv4PolicyIPRange.md)

[Set-DhcpServerv4Policy](./Set-DhcpServerv4Policy.md)

