---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerV4OptionDefinition_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv4optiondefinition?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DhcpServerv4OptionDefinition
---

# Get-DhcpServerv4OptionDefinition

## SYNOPSIS
Gets the DHCPv4 option definition for the specified option IDs.

## SYNTAX

```
Get-DhcpServerv4OptionDefinition [-ComputerName <String>] [[-OptionId] <UInt32[]>] [[-VendorClass] <String>]
 [-All] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DhcpServerv4OptionDefinition** cmdlet gets the DHCPv4 option definitions for the specified option identifiers (IDs).

If you do not specify the *OptionId* parameter, all of the option definitions, which are not vendor specific, are returned.
The *VendorClass* parameter acts as a filter for option definitions for the specified vendor class only.

If you specify the *All* parameter, all of the option definitions including the vendor class specific option definitions are returned.

If you specify the *All* and *OptionId* parameters, all of the option definitions including the vendor class specific option definitions with the specified option ID are be returned.

If you specify the *All* and the *VendorClass* parameters, the *All* parameter is ignored.

## EXAMPLES

### Example 1: Get standard DHCPv4 option definitions
```
PS C:\> Get-DhcpServerv4OptionDefinition -ComputerName "dhcpserver.contoso.com"
```

This example gets the standard, or non-vendor specific, DHCPv4 option definitions on the DHCP server service that runs on the computer named dhcpserver.contoso.com.

### Example 2: Get all DHCPv4 option definitions
```
PS C:\> Get-DhcpServerv4OptionDefinition -ComputerName "dhcpserver.contoso.com" -All
```

This example gets all of the DHCPv4 option definitions including vendor specific option definition present on the DHCP server service.

### Example 3: Get DHCPv4 option definition for an option
```
PS C:\> Get-DhcpServerv4OptionDefinition -ComputerName "dhcpserver.contoso.com" -OptionId 23
```

This example gets the DHCPv4 option definition for the specified option.

### Example 4: Get all DHCPv4 option definitions for a vendor class
```
PS C:\> Get-DhcpServerv4OptionDefinition -ComputerName "dhcpserver.contoso.com" -VendorClass "Microsoft Windows Options"
```

This example gets all the DHCPv4 option definitions for the specified vendor class.

## PARAMETERS

### -All
Indicates that this cmdlet gets all of the option definitions on the DHCP server service including vendor specific option definitions.

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

### -OptionId
Specifies the numeric identifiers of the options for which the option definitions are requested.
If you do not specify this parameter, all of the DHCPv4 option definitions are returned.

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

### -VendorClass
Returns the option definitions only for the specified vendor class.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4OptionValue
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4OptionDefinition[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4OptionDefinition](./Add-DhcpServerv4OptionDefinition.md)

[Remove-DhcpServerv4OptionDefinition](./Remove-DhcpServerv4OptionDefinition.md)

[Set-DhcpServerv4OptionDefinition](./Set-DhcpServerv4OptionDefinition.md)

