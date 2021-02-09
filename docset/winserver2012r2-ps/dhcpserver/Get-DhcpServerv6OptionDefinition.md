---
external help file: PS_DhcpServerV6OptionDefinition_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
online version: 
schema: 2.0.0
title: Get-DhcpServerv6OptionDefinition
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 3087D2C8-5321-4D00-A55F-7F569DBB8940
---

# Get-DhcpServerv6OptionDefinition

## SYNOPSIS
Gets the option definition for the option identified by the option identifier (ID).

## SYNTAX

```
Get-DhcpServerv6OptionDefinition [-ComputerName <String>] [[-OptionId] <UInt32[]>] [[-VendorClass] <String>]
 [-All] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DhcpServerv6OptionDefinition** cmdlet gets the option definition for the option identified by the option identifier (ID).
If the **OptionId** parameter is not specified, then all of the option definitions will be returned.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-DhcpServerv6OptionDefinition -ComputerName dhcpserver.contoso.com
```

This example gets all of the DHCPv6 option definitions present on the DHCP server service.

### EXAMPLE 2
```
PS C:\> Get-DhcpServerv6OptionDefinition -ComputerName dhcpserver.contoso.com -OptionId 21,24
```

This example gets the DHCPv6 option definitions for the specified option IDs.

### EXAMPLE 3
```
PS C:\> Get-DhcpServerv6OptionDefinition -ComputerName dhcpserver.contoso.com -VendorClass MyVendorClass
```

This example gets all of the DHCPv6 option definitions for the specified vendor class.

## PARAMETERS

### -All
Gets all of the option definitions on the DHCPv6 server service.
Option definitions which are vendor class specific will also be returned.

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

### -OptionId
Specifies the numeric ID of the option.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/Dhcpv6OptionDefinition
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/Dhcpv6OptionValue
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6OptionDefinition[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv6OptionDefinition](./Add-DhcpServerv6OptionDefinition.md)

[Remove-DhcpServerv6OptionDefinition](./Remove-DhcpServerv6OptionDefinition.md)

[Set-DhcpServerv6OptionDefinition](./Set-DhcpServerv6OptionDefinition.md)

