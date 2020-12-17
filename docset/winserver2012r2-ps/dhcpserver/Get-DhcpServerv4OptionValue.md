---
external help file: PS_DhcpServerV4OptionValue_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
online version: 
schema: 2.0.0
title: Get-DhcpServerv4OptionValue
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
ms.assetid: 387170C5-037D-4C73-B0E7-A01D5F2CEE93
---

# Get-DhcpServerv4OptionValue

## SYNOPSIS
Returns the IPv4 option Values for one or more IPv4 options at the server, scope or reservation level.

## SYNTAX

```
Get-DhcpServerv4OptionValue [-VendorClass <String>] [-ComputerName <String>] [[-ScopeId] <IPAddress>]
 [-ReservedIP <IPAddress>] [[-OptionId] <UInt32[]>] [-UserClass <String>] [-All] [-Brief]
 [-PolicyName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DhcpServerv4OptionValue** cmdlet returns the IPv4 option values for one or more IPv4 options at the server, scope or reservation level.
Use the **VendorClass** and **UserClass** parameters to get option values for a specific vendor class or for a specific user class.
If the **OptionId** parameter is not specified, then this cmdlet returns the option values for all the options configured at the specified level either the server, the scope, or the reservation level.

If only the **ReservedIP** parameter is specified, then the option values set at the rReservation level are returned.
If only the **ScopeId** parameter is specified, then the option values set at the scope level are returned.
If neither the **ScopeId** nor the **ReservedIP** parameter are specified, then option values set at the server level are returned.

If neither the **VendorClass** nor **UserClass** parameter is specified, then this cmdlet gets the standard option values set.

The **PolicyName** and **UserClass** parameters cannot both be specified.

The **PolicyName** parameter cannot be specified if the **ReservedIP** parameter is specified.

Note: The option values for policies only exist for DHCP server services running on Windows Server® 2012.
For older versions, only user class based option values exist.

To get legacy user class options, the **UserClass** parameter must be specified.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com
```

This example gets all the standard DHCPv4 option values, or non-class specific, configured at the server level.

### EXAMPLE 2
```
PS C:\> Get-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0
```

This example gets all the standard DHCPv4 option values, or non-class specific, configured for the specified scope.

### EXAMPLE 3
```
PS C:\> Get-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ReservedIP 10.10.10.5
```

This example gets all of the standard DHCPv4 option values, or non-class specific, configured for the specified reservation.

### EXAMPLE 4
```
PS C:\> Get-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -VendorClass MSUCClient
```

This example gets all of the vendor class specific DHCPv4 option values configured on the specified scope for the specified vendor class.

### EXAMPLE 5
```
PS C:\> Get-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -OptionId 23
```

This example gets the DHCPv4 option value configured on the specified scope for the specified option ID.

### EXAMPLE 6
```
PS C:\> Get-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -All
```

This example gets all of the DHCPv4 option values, including standard as well as vendor class or user class specific, configured on the specified scope.

### EXAMPLE 7
```
PS C:\> Get-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -Brief
```

This example gets all of the standard DHCPv4 option values configured on the specified scope.
The object that is returned does not contain the name of the option.
The **Brief** parameter increase the performance by removing the delay required to get the name of the option from the DHCP server service.

### EXAMPLE 8
```
PS C:\> Get-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -UserClass LabComputer
```

This example gets all of the user class specific DHCPv4 option values configured on the specified scope for the specified user class.

### EXAMPLE 9
```
PS C:\> Get-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -Policy SmartPhonePolicy
```

This example gets all of the standard DHCPv4 option values configured on the specified scope for the specified policy.

### EXAMPLE 10
```
PS C:\> Get-DhcpServerv4OptionValue -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -Policy SmartPhonePolicy -VendorClass "HTC Phone"
```

This example gets all of the standard, or non-class specific, DHCPv4 option values configured on the specified scope for the specified policy and vendor class.

## PARAMETERS

### -All
Gets the option values for a scope, server, or reservation.
Option values can include vendor class, user class, and policy specific. 
                         
If only this parameter is specified, then this cmdlet will get all of the option values for a scope, server, or reservation. 
                         
If the **OptionId** parameter and this parameter are specified, then option values for the specified option identifier (ID) for all of the vendor classes, user classes and policies will be returned. 
                         
If the **VendorClass** parameter and this parameter are specified, then all of the option values for the specified vendor class including those for any user class or policy would be returned. 
                         
If the **UserClass** parameter and this parameter are specified, then all of the option values for the specified user class including any vendor specific options would be returned. 
                         
If the **PolicyName** parameter and this parameter are specified, then all of the option values for the specified policy including any vendor specific options would be returned.

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

### -Brief
Specifies that the name of the option is not returned in the option value object.
This parameter improves the performance of this cmdlet by not requesting the name of the option from the DHCP server service.
For repeatedly fetching a large number of option values with this cmdlet use of the **Brief** parameter is recommended.

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
Specifies the numerical IDs of the options being requested.

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

### -PolicyName
Specifies the name of the policy for which one or more option values are requested.

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
Specifies the IPv4 address of the reservation for which the option values are requested.

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
Specifies the ID of the scope, in IP address format, for which one or more option values are requested.

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
Gets the option values for that user class.

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
Gets the option values for that vendor class.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4OptionDefinition
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Policy
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Reservation
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstanceroot/Microsoft/Windows/DHCP/DhcpServerv4OptionValue[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Remove-DhcpServerv4OptionValue](./Remove-DhcpServerv4OptionValue.md)

[Set-DhcpServerv4OptionValue](./Set-DhcpServerv4OptionValue.md)

