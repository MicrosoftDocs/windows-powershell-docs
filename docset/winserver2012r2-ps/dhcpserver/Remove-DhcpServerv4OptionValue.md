---
external help file: PS_DhcpServerV4OptionValue_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
online version: 
schema: 2.0.0
title: Remove-DhcpServerv4OptionValue
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 48C34EAD-30C7-4F3D-A696-3FAF11F83004
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

If only the **ReservedIP** parameter is specified, then the option values set at the reservation level are deleted.
If only the **ScopeId** parameter is specified, then the option values set at the scope level are deleted.
If neither the **ScopeId** nor the **ReservedIP** parameter is specified, then the option values set at the server level are deleted.
The **ScopeId** and the **ReservedIP** parameters cannot both be specified.

The **UserClass** and **PolicyName** parameters cannot both be specified.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -OptionId 23
```

This example deletes DHCPv4 option value configured on the specified scope for the specified option ID.

### EXAMPLE 2
```
PS C:\>Remove-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -VendorClass MSUCClient -OptionId 5
```

This example deletes DHCPv4 option value configured on the specified scope for the specified vendor class named MSUCClient with the specific option 5.

### EXAMPLE 3
```
PS C:\>Remove-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -PolicyName SmartPhonePolicy -OptionId 252
```

This example deletes DHCPv4 option value with the option ID 252 configured for the specified policy in the scope 10.10.10.0.

### EXAMPLE 4
```
PS C:\>Remove-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -UserClass LabComputer -OptionId 252
```

This example deletes DHCPv4 option value with the option ID 252 configured for the specified user class in the scope 10.10.10.0.

### EXAMPLE 5
```
PS C:\>Remove-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -OptionId 23
```

This example deletes DHCPv4 option value configured at the server level, or server-wide, for the specified option ID.

### EXAMPLE 6
```
PS C:\>Remove-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -VendorClass MSUCClient -OptionId 5
```

This example deletes DHCPv4 option value configured at the server level, or server-wide, for the specified vendor class named MSUCClient with the specific option 5.

### EXAMPLE 7
```
PS C:\>Remove-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -PolicyName SmartPhonePolicy -OptionId 252
```

This example deletes DHCPv4 option value with the option ID 252 configured for the specified policy at the server level, or server-wide.

### EXAMPLE 8
```
PS C:\>Remove-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -UserClass LabComputer -OptionId 252
```

This example deletes DHCPv4 option value with the option ID 252 configured for the specified user class at the server level, or server-wide.

### EXAMPLE 9
```
PS C:\>Remove-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ReservedIP 10.10.10.5 -OptionId 23
```

This example deletes DHCPv4 option value configured on the specified reservation for the specified option ID.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

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

