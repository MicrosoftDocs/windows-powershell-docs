---
author: Kateyanne
description: 
external help file: PS_DhcpServerv6Class_v1.0.0.cdxml-help.xml
manager: jasgro
Module Name: DhcpServer
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv6class?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DhcpServerv6Class
---

# Get-DhcpServerv6Class

## SYNOPSIS
Gets the IPv6 vendor or user class from the Dynamic Host Configuration Protocol (DHCP) server service.

## SYNTAX

```
Get-DhcpServerv6Class [[-Name] <String[]>] [[-Type] <String>] [-ComputerName <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DhcpServerv6Class** cmdlet gets the IPv6 vendor or user class from the Dynamic Host Configuration Protocol (DHCP) server service.

If only the **Type** parameter is specified, then all of the classes of the specified class type on the DHCP server service are retrieved.

If neither the **Name** nor the **Type** parameter is specified, then all of the user and vendor classes on the DHCP server service are retrieved.

If only the **Name** parameter is specified, then the class for that **Name** parameter value will be returned.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DhcpServerv6Class -ComputerName dhcpserver.contoso.com
```

This example gets all of the DHCPv6 class definitions, both vendor and user, which are present on the DHCP server service.

### EXAMPLE 2
```
PS C:\>Get-DhcpServerv6Class -ComputerName dhcpserver.contoso.com -Type Vendor
```

This example gets all of the DHCPv6 vendor class definitions which are present on the DHCP server service.

### EXAMPLE 3
```
PS C:\>Get-DhcpServerv6Class -ComputerName dhcpserver.contoso.com -Name MSUCClient
```

This example gets the DHCPv6 vendor class definition for the vendor class named MSUCClient.

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

### -Name
Specifies the name of the vendor or user class which is to be retrieved.

```yaml
Type: String[]
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

### -Type
Specifies the type of the class.
The acceptable values for this parameter are: Vendor or User.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Vendor, User

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Class
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Class[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv6Class](./Add-DhcpServerv6Class.md)

[Remove-DhcpServerv6Class](./Remove-DhcpServerv6Class.md)

[Set-DhcpServerv6Class](./Set-DhcpServerv6Class.md)

