---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerV4Reservation_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/add-dhcpserverv4reservation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DhcpServerv4Reservation
---

# Add-DhcpServerv4Reservation

## SYNOPSIS
Reserves an IPv4 address in the scope for a client.

## SYNTAX

```
Add-DhcpServerv4Reservation [-ComputerName <String>] [-ScopeId] <IPAddress> [-IPAddress] <IPAddress>
 [-ClientId] <String> [-Name <String>] [-Description <String>] [-Type <String>] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DhcpServerv4Reservation** cmdlet reserves the specified IPv4 address in the scope for a client.
Once reserved, the IP address is leased only to the client identified by the specific client identifier (ID).

## EXAMPLES

### Example 1: Add a reserved IP address
```
PS C:\> Add-DhcpServerv4Reservation -ScopeId 10.10.10.0 -IPAddress 10.10.10.8 -ClientId "F0-DE-F1-7A-00-5E" -Description "Reservation for Printer"
```

This example adds a reserved IP address for the client identified by the specified client ID.

### Example 2: Add reservations from a file
```
PS C:\> Import-Csv -Path "Reservations.csv" | Add-DhcpServerv4Reservation -ComputerName "dhcpserver.contoso.com"
```

This example adds all of the reservations in the file that is named Reservations.csv to the DHCP server service that runs on the computer named dhcpserver.contoso.com.
The **Import-Csv** cmdlet returns the objects that have reservation fields and pipes the objects to this cmdlet, which adds these reservations to the DHCP server services.
The file that is named Reservations.csv should contain the reservations in the following comma-separated values (CSV) format:

ScopeId,IPAddress,Name,ClientId,Description

10.10.10.0,10.10.10.10,Computer1,1a-1b-1c-1d-1e-1f,Reserved for Computer1

20.20.20.0,20.20.20.11,Computer2,2a-2b-2c-2d-2e-2f,Reserved for Computer2

30.30.30.0,30.30.30.12,Computer3,3a-3b-3c-3d-3e-3f,Reserved for Computer3

### Example 3: Convert a lease to a reservation
```
PS C:\> Get-DhcpServerv4Lease -ComputerName "dhcpserver.contoso.com" -IPAddress 10.10.10.11 | Add-DhcpServerv4Reservation -ComputerName "dhcpserver.contoso.com"
```

This example converts one of the leases into a reservation.
The **Get-DhcpServerv4Lease** cmdlet returns the IP address lease object and pipes the object to this cmdlet, which creates the reservation with the IP address and client ID in the lease object.

### Example 4: Create a reservation in a scope
```
PS C:\> $FreeIP = Get-DhcpServerv4FreeIPAddress -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0
PS C:\> Add-DhcpServerv4Reservation -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -IPAddress $FreeIP -ClientId "F0-DE-F1-7A-00-5E" -Description "Reservation for Printer"
```

This example creates a reservation for the client identified by the specified client ID from any of the free IP addresses in the scope 10.10.10.0.
The **Get-DhcpServerv4FreeIPAddress** cmdlet gets a free IP address in the scope, and then this cmdlet reserves an address for the specified client ID.

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

### -ClientId
Specifies the unique identifier (ID) for the client.
For Windows clients, the MAC address is used as the client ID.

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

### -ComputerName
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer that runs the Dynamic Host Configuration Protocol (DHCP) server service.

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
Specifies the description for the reservation to created.

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
Specifies the IPv4 address to reserve for the client.

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

### -Name
Specifies the name of the reservation created.
This parameter value can be the host name of the client or a name to identify the reservation on the DHCP server service.

```yaml
Type: String
Parameter Sets: (All)
Aliases: HostName, ReservationName

Required: False
Position: Named
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

### -ScopeId
Specifies the identifier (ID) of the scope in which the reservation is created.

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

### -Type
Specifies the type of client request for which this IP address is reserved.
The acceptable values for this parameter are: DHCP, BootP, or Both.
The default value is Both.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ReservationType
Accepted values: Dhcp, Bootp, Both

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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Lease
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Reservation
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Reservation
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DhcpServerv4FreeIPAddress](./Get-DhcpServerv4FreeIPAddress.md)

[Get-DhcpServerv4Lease](./Get-DhcpServerv4Lease.md)

[Get-DhcpServerv4Reservation](./Get-DhcpServerv4Reservation.md)

[Remove-DhcpServerv4Reservation](./Remove-DhcpServerv4Reservation.md)

[Set-DhcpServerv4Reservation](./Set-DhcpServerv4Reservation.md)

