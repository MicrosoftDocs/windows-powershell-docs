---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerV4Reservation_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv4reservation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DhcpServerv4Reservation
---

# Get-DhcpServerv4Reservation

## SYNOPSIS
Gets IPv4 reservations for IP addresses or client IDs.

## SYNTAX

### ScopeId (Default)
```
Get-DhcpServerv4Reservation [-ComputerName <String>] [-ScopeId] <IPAddress> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### IPAddress
```
Get-DhcpServerv4Reservation [-ComputerName <String>] -IPAddress <IPAddress[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ClientId
```
Get-DhcpServerv4Reservation [-ComputerName <String>] [-ClientId] <String[]> [-ScopeId] <IPAddress>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DhcpServerv4Reservation** cmdlet gets one or more IPv4 reservations for the specified IP addresses or client identifiers (IDs).
If only the *ScopeId* parameter is specified, all of the IPv4 reservations from the specified scope are returned.

## EXAMPLES

### Example 1: Get reservations in a specified scope
```
PS C:\> Get-DhcpServerv4Reservation -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0
```

This cmdlet gets all of the reservations present in the specified scope on the specified DHCP server service that runs on the computer named dhcpserver.contoso.com.

### Example 2: Get a reservation for a specified client
```
PS C:\> Get-DhcpServerv4Reservation -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -ClientId "F0-DE-F1-7A-00-5E"
```

This cmdlet gets the reservation present in the specified scope for specified client ID.

### Example 3: Get a reservation information for a specified address
```
PS C:\> Get-DhcpServerv4Reservation -ComputerName "dhcpserver.contoso.com" -IPAddress 10.10.10.5
```

This cmdlet gets the reservation information for specified IP address.

### Example 4: Get all reservations for all scopes
```
PS C:\> Get-DhcpServerv4Scope -ComputerName dhcpserver.contoso.com | Get-DhcpServerv4Reservation -ComputerName dhcpserver.contoso.com
```

This cmdlet gets all the reserved IP addresses from all of the scopes on the server dhcpserver.contoso.com.
The **Get-DhcpServerv4Scope** cmdlet returns all of the scope objects and pipes the objects into this cmdlet, which returns the reservations from all the scopes.

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
Specifies one or more client IDs of the reservations which need to be retrieved.
For Windows clients, the MAC address is the client ID.

```yaml
Type: String[]
Parameter Sets: ClientId
Aliases:

Required: True
Position: 2
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

### -IPAddress
Specifies one or more IPv4 addresses of the reservations which are to be retrieved.

```yaml
Type: IPAddress[]
Parameter Sets: IPAddress
Aliases: ReservedIP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScopeId
Specifies the scope ID, in IPv4 address format, from which the reservations are to be retrieved.

```yaml
Type: IPAddress
Parameter Sets: ScopeId, ClientId
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Reservation
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Reservation[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4Reservation](./Add-DhcpServerv4Reservation.md)

[Get-DhcpServerv4Scope](./Get-DhcpServerv4Scope.md)

[Remove-DhcpServerv4Reservation](./Remove-DhcpServerv4Reservation.md)

[Set-DhcpServerv4Reservation](./Set-DhcpServerv4Reservation.md)

