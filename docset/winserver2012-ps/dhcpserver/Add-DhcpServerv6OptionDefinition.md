---
external help file: DhcpServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 18605C7A-EFE8-4C59-B819-F94015E39E84
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Add-DhcpServerv6OptionDefinition

## SYNOPSIS
Adds a DHCPv6 option definition to a Dynamic Host Configuration Protocol (DHCP) server service running on the local or a remote computer.

## SYNTAX

```
Add-DhcpServerv6OptionDefinition [-Name] <String> [-OptionId] <UInt32> [-Type] <String> [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-DefaultValue <String[]>] [-Description <String>]
 [-MultiValued] [-PassThru] [-ThrottleLimit <Int32>] [-VendorClass <String>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-DhcpServerv6OptionDefinition** cmdlet adds a DHCPv6 option definition to a Dynamic Host Configuration Protocol (DHCP) server service running on the local or a remote computer.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Add-DhcpServerv6OptionDefinition -Name "Broadcast and Multicast Service Controller IPv6 Address" -OptionId 36 -Type IPv6Address
```

This example adds the Broadcast and Multi-cast Service Controller IPv6 Address option definition to the DHCPv6 server service.

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

### -DefaultValue
Specifies the default value for the option. 

If the type of the option is Byte, Word, DWord, or DWordDword, then the default value must be specified as one or more decimal or hexadecimal strings. 

If the type of the option is IPAddress or IPv6Address, then the default value must be specified as an IP address string. 

If the type of the option is String, then the default value must be specified as a string. 

If the type of the option is BinaryData or EncapsulatedData, then the default value must be specified as a hexadecimal string.

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

### -Description
Specifies the description of the option definition.

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

### -MultiValued
Specifies that the option allows multiple values to be specified.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the option.

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

### -OptionId
Specifies the integer identifier (ID) for the option.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

### -Type
Specifies the data type of the option.
The acceptable values for this parameter are: Byte, Word, DWord, DWordDword, IPAddress, String, BinaryData, EncapsulatedData, or IPv6Address.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VendorClass
Adds the option definition only for the specified vendor class.

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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6OptionDefinition
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DhcpServerv6OptionDefinition](./Get-DhcpServerv6OptionDefinition.md)

[Remove-DhcpServerv6OptionDefinition](./Remove-DhcpServerv6OptionDefinition.md)

[Set-DhcpServerv6OptionDefinition](./Set-DhcpServerv6OptionDefinition.md)

