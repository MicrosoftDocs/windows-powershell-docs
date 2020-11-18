---
external help file: DhcpServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: A569B764-3CBF-4A35-A4E2-26EF27B34FAB
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-DhcpServerv4Reservation

## SYNOPSIS
Gets one or more IPv4 reservations for the specified IP addresses or client identifiers (IDs).

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-DhcpServerv4Reservation [-ScopeId] <IPAddress> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-DhcpServerv4Reservation [-ScopeId] <IPAddress> [-ClientId] <String[]> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-DhcpServerv4Reservation [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-ThrottleLimit <Int32>] -IPAddress <IPAddress[]>
```

## DESCRIPTION
The **Get-DhcpServerv4Reservation** cmdlet gets one or more IPv4 reservations for the specified IP addresses or client identifiers (IDs).
If only the **ScopeId** parameter is specified, then all of the IPv4 reservations from the specified scope are returned.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DhcpServerv4Reservation -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0.
```

This cmdlet gets all of the reservations present in the specified scope on the specified DHCP server service running on the computer named dhcpserver.contoso.com.

### EXAMPLE 2
```
PS C:\>Get-DhcpServerv4Reservation -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -ClientId F0-DE-F1-7A-00-5E
```

This cmdlet gets the reservation present in the specified scope for specified client ID.

### EXAMPLE 3
```
PS C:\>Get-DhcpServerv4Reservation -ComputerName dhcpserver.contoso.com -IPAddress 10.10.10.5
```

This cmdlet gets the reservation information for specified IP address.

### EXAMPLE 4
```
PS C:\>Get-DhcpServerv4Scope -ComputerName dhcpserver.contoso.com | Get-DhcpServerv4Reservation -ComputerName dhcpserver.contoso.com
```

This cmdlet gets all the reserved IP addresses from all of the scopes on the server dhcpserver.contoso.com.
The Get-DhcpServerv4Scope cmdlet returns all of the scope objects and pipes the objects into this cmdlet, which returns the reservations from all the scopes.

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

### -ClientId
Specifies one or more client IDs of the reservations which need to be retrieved.
For Windows clients, the MAC address is the client ID.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the Dynamic Host Configuration Protocol (DHCP) server service.

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

### -IPAddress
Specifies one or more IPv4 addresses of the reservations which are to be retrieved.

```yaml
Type: IPAddress[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

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

