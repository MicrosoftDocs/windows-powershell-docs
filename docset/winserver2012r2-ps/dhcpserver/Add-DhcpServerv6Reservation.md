---
external help file: PS_DhcpServerV6Reservation_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
online version: 
schema: 2.0.0
title: Add-DhcpServerv6Reservation
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: D1B1F504-0087-4DBE-8C99-0A364ADA0663
---

# Add-DhcpServerv6Reservation

## SYNOPSIS
Adds an IPv6 Reservation to an IPv6 prefix or scope.

## SYNTAX

```
Add-DhcpServerv6Reservation [-ComputerName <String>] [-IPAddress] <IPAddress> [-ClientDuid] <String>
 [-Iaid] <UInt32> [[-Name] <String>] [-Description <String>] [-Prefix] <IPAddress> [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DhcpServerv6Reservation** cmdlet reserves a specified IPv6 address for the client identified by the specified Dynamic Host Configuration Protocol (DHCP) v6 unique identifier (ID) (DUID) and identity association ID (IAID).

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Add-DhcpServerv6Reservation -Prefix 2001:4898:7020:1020:: -IPAddress 2001:4898:7020:1020::1 -ClientDuid 00-01-00-01-15-F9-7F-AB-F0-DE-F1-7A-00-5E -Iaid 234890455
```

This example reserves the specified IPv6 address for the specified **ClientDuid** and **Iaid** parameter values.
After the reservation is added, the DHCP server service will assign only the specified IP address to the client request which contains the specified **ClientDuid** and **Iaid** parameter values.

### EXAMPLE 2
```
PS C:\> Import-Csv -Path Reservations.csv | Add-DhcpServerv6Reservation -ComputerName dhcpserver.contoso.com
```

This example adds all of the reservations in the file named Reservations.csv to the DHCP server service running on the computer named dhcpserver.contoso.com.
The Import-Csvhttp://go.microsoft.com/fwlink/p/?LinkId=113341 cmdlet returns the objects with reservation fields and pipes the objects to this cmdlet, which adds these reservations to the DHCP server service.
The file named Reservations.csv should contain the reservations in the following comma-separated values (CSV) format:

Prefix,IPAddress,Name,ClientDuid,Iaid,Description 

2001:4898:7020:1020::,2001:4898:7020:1020::1,Computer1,00-01-00-01-15-F9-7F-AB-F0-DE-F1-7A-00-5E,234890455,Reserved for Computer1 

2001:4898:7020:1020::,2001:4898:7020:1020::2,Computer2,00-01-00-01-15-F9-7F-AB-F0-DE-F1-7A-00-6E,234890465,Reserved for Computer2 

2001:4898:7020:1020::,2001:4898:7020:1020::3,Computer3,00-01-00-01-15-F9-7F-AB-F0-DE-F1-7A-00-7E,234890475,Reserved for Computer3

### Example 3
```
PS C:\> $freeip = Get-DhcpServerv6FreeIPAddress -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020::
PS C:\> Add-DhcpServerv6Reservation -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020:: -IPAddress $freeip -ClientDuid 00-01-00-01-15-F9-7F-AB-F0-DE-F1-7A-00-5E -Iaid 234890455 -Description "Reservation for Printer"
```

This example creates a reservation for the client identified by the specified client ID from any of the free IP address in the scope 2001:4898:7020:1020::.
The Get-DhcpServerv6FreeIPAddress cmdlet fetches a free IP address in that scope, then this cmdlet reserves the IP address for the specified client ID.

### EXAMPLE 4
```
PS C:\> Get-DhcpServerv6Lease -ComputerName dhcpserver.contoso.com -IPAddress 2001:4898:7020:1020::11 | Add-DhcpServerv6Reservation -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020::
```

This example converts one of the leases into a reservation.
The Get-DhcpServerv6Lease cmdlet returns an IP address lease object and pipes the object to this cmdlet, which creates the reservation with the IP address, client DUID, and IAID in the lease object.

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

### -ClientDuid
Specifies the DUID of the client.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Duid

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the DHCP server service.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn, ReservationServer

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

### -Description
Specifies the description string for the IPv6 reservation being created.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ReservationDescription

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPAddress
Specifies the IPv6 address to be reserved for the client.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: ReservedIP

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Iaid
Specifies the DHCPv6 IAID of a specific network interface of the client.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the client.
This parameter value can be the actual host name of the client or a name assigned to identify the reserved client on the DHCP server service.

```yaml
Type: String
Parameter Sets: (All)
Aliases: HostName, ReservationName

Required: False
Position: 5
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

### -Prefix
Specifies the IPv6 prefix which identifies the scope in which the reservation is created.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: ReservationScopeID

Required: True
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Reservation
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Reservation
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Import-Csv](https://go.microsoft.com/fwlink/p/?LinkId=113341)

[Get-DhcpServerv6FreeIPAddress](./Get-DhcpServerv6FreeIPAddress.md)

[Get-DhcpServerv6Lease](./Get-DhcpServerv6Lease.md)

[Get-DhcpServerv6Reservation](./Get-DhcpServerv6Reservation.md)

[Remove-DhcpServerv6Reservation](./Remove-DhcpServerv6Reservation.md)

[Set-DhcpServerv6Reservation](./Set-DhcpServerv6Reservation.md)

