---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerV4OptionDefinition_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/add-dhcpserverv4optiondefinition?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DhcpServerv4OptionDefinition
---

# Add-DhcpServerv4OptionDefinition

## SYNOPSIS
Adds a DHCPv4 option definition on the DHCP server service.

## SYNTAX

```
Add-DhcpServerv4OptionDefinition [-ComputerName <String>] [-Name] <String> [-Description <String>]
 [-OptionId] <UInt32> [-Type] <String> [-MultiValued] [-VendorClass <String>] [-DefaultValue <String[]>]
 [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-DhcpServerv4OptionDefinition** cmdlet adds a new DHCPv4 option definition on the Dynamic Host Configuration Protocol (DHCP) server service.
An option definition must exist before an option value of that type can be configured.

## EXAMPLES

### Example 1: Add the IPv4 option definition for web proxy auto detection
```
PS C:\> Add-DhcpServerv4OptionDefinition -Name "WPAD" -OptionId 252 -Type "String"
```

This example adds the IPv4 option definition for web proxy auto detection (wpad) to the DHCPv4 server service.

### Example 2: Add the option definition for the UC identifier for a vendor class
```
PS C:\> Add-DhcpServerv4OptionDefinition -Name "UCIdentifier" -OptionId 1 -Type "BinaryData" -VendorClass "MS-UC-Client" -Description "UC Identifier"
```

This example adds the option definition for the Unified Communications (UC) identifier for the vendor class named MS-UC-Client.

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

### -DefaultValue
Specifies the default value for the option for which a definition is created.
The syntax to specify the default value for the option as follows: 

- Byte, Word, DWord, DWordDword.
These values can be specified as decimal or hexadecimal strings. 
- IPAddress, IPv6Address.
These values can be specified as IP address strings. 
- String.
This value can be specified as a string. 
- BinaryData, EncapsulatedData.
These values can be specified as hexadecimal strings.

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
Specifies the description of the option definition being added.

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
Allows for multiple values.

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
Specifies the name of the DHCPv4 option.

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
Specifies the numeric identifier of the option.
The acceptable values for this parameter are: 1 through 255.

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
Specifies the data type of the values for this option.
The acceptable values for this parameter are:

- Byte 
- Word 
- DWord 
- DWordDword 
- IPAddress 
- String 
- BinaryData 
- EncapsulatedData 
- IPv6Address

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Byte, Word, DWord, DWordDWord, IPv4Address, IPv6Address, String, BinaryData, EncapsulatedData

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VendorClass
Adds the Option Definition for the specified vendor class.

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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4OptionDefinition
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4OptionValue
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4OptionDefinition
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DhcpServerv4OptionDefinition](./Get-DhcpServerv4OptionDefinition.md)

[Remove-DhcpServerv4OptionDefinition](./Remove-DhcpServerv4OptionDefinition.md)

[Set-DhcpServerv4OptionDefinition](./Set-DhcpServerv4OptionDefinition.md)

