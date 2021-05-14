---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://docs.microsoft.com/powershell/module/dhcpserver/set-dhcpserverv4policy?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DhcpServerv4Policy

## SYNOPSIS
Sets the properties of an existing policy either at the server level or at the specified scope level.

## SYNTAX

```
Set-DhcpServerv4Policy [-Name] <String> [[-ScopeId] <IPAddress>] [-AsJob] [-CimSession <CimSession[]>]
 [-CircuitId <String[]>] [-ClientId <String[]>] [-ComputerName <String>] [-Condition <String>]
 [-Description <String>] [-Enabled <Boolean>] [-MacAddress <String[]>] [-NewName <String>] [-PassThru]
 [-ProcessingOrder <UInt16>] [-RelayAgent <String[]>] [-RemoteId <String[]>] [-SubscriberId <String[]>]
 [-ThrottleLimit <Int32>] [-UserClass <String[]>] [-VendorClass <String[]>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-DhcpServerv4Policy** cmdlet sets the properties of an existing policy either at the server level or at the specified scope level.
If the **VendorClass**, **UserClass**, **MacAddress**, **ClientId**, **RelayAgent**, **CircuitId**, **RemoteId** or **SubscriberId** parameter are specified, then the conditions of the policy are being changed and this cmdlet will behave as follows:

If the **VendorClass** parameter is specified and the policy being modified already has conditions for the **VendorClass** parameter value, then the existing **VendorCass** parameter value is removed and the new **VendorClass** parameter value will be added.

However, if the policy being modified has conditions for the **MacAddress** parameter value, then the **MacAddress** parameter value is not altered and is logically combined (ORꞌd) or differenced (ANDꞌd) with the vendor class based conditions.

The same applies to any of the **VendorClass**, **UserClass**, **MacAddress**, **ClientId**, **RelayAgent**, **CircuitId**, **RemoteId** and **SubscriberId** parameters used in the conditions.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-DhcpServerv4Policy -ComputerName dhcpserver.contoso.com -Name DevicesPolicy -NewName TabletPolicy -Description "policy for tablet devices" -ProcessingOrder 4 -Enabled False
```

This example renames the server level policy named DevicesPolicy to TabletPolicy, sets a description string, disables the policy, and sets the processing order to 4.

### EXAMPLE 2
```
PS C:\>Set-DhcpServerv4Policy -Name PhysicalMachinesPolicy -Condition OR -MacAddress NE,00155D*,000569*
```

This example modifies the conditions of the server level policy for non-Hyper-V clients.
If the policy had an existing MAC address based condition, then the same condition is replaced with the condition specified in this cmdlet.
However, if the policy had conditions based on other fields, such as the **VendorClass**, **UserClass**, **ClientId**, or **RelayAgent** parameters, then those will be retained and logically combined (ORꞌd) with the newly added MAC address based condition.

### EXAMPLE 3
```
PS C:\>Set-DhcpServerv4Policy -Name PhysicalMachinesPolicy -Condition OR -MacAddress NE,00155D*,000569* -VendorClass ""
```

This example modifies the conditions of the server level policy for non-Hyper-V clients.
If the policy had an existing MAC address based condition, a vendor class based policy, or both, then the conditions are replaced with the condition specified in this cmdlet.

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

### -CircuitId
Specifies the comparator to use and the values with which to compare the circuit identifier (ID) sub-option.
The first element is the comparator, EQ or NE, followed by a single value.
No wildcards characters are allowed. 

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
If the last character in a value is an asterisk (`*`), then the following characters are treated as wildcard characters for the comparison. 

The values can be followed by another comparator, EQ or NE, which is followed by another set of values. 

The input format is a hexadecimal string with or without hyphen separation.
The output format is a hexadecimal string with hyphen separation. 

The values following the EQ operator will be treated as multiple assertions which are logically combined (ORꞌd). 

The values following the NE operator will be treated as multiple assertions which are logically differenced (ANDꞌd). 

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
Aliases: 

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

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
The acceptable values for this parameter are: True or False.

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

### -MacAddress
Specifies the comparator to use and the values with which to compare the MAC Address in the client request.
The first element is the comparator, EQ or NE, followed by a set of values.
If the last character in the value is an asterisk (`*`), then the following characters are treated as wildcard characters for the comparison. 

The values can be followed by another comparator, EQ or NE, which is followed by another set of values. 

The input format is a hexadecimal string with or without hyphen separation.
A trailing wildcard character can be used to indicate partial match.
The output format is a hexadecimal string with hyphen separation. 

The values following the EQ operator will be treated as multiple assertions which are logically combined (ORꞌd). 

The values following the NE operator will be treated as multiple assertions which are logically differenced (ANDꞌd). 

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
Specifies the order for this policy with respect to other policies in the scope or DHCP server service.
The DHCP server service will process the policies in the specified order while evaluating client requests using the configured policies.

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
No wildcard characters are allowed. 

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
No wildcard characters are allowed. 

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
If this parameter is not specified, then the server level policy is modified.

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
No wildcard characters are allowed. 

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
If the last character in the value is an asterisk (`*`), then the subsequent characters are treated as wildcard characters for the comparison. 

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
If the last character in a value is an asterisk (`*`), then the subsequent characters are treated as wildcard characters for the comparison. 

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

