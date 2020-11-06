---
external help file: DhcpServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: F76E414E-5562-4E98-9413-67D00AFE5878
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-DhcpServerv4Lease

## SYNOPSIS
Gets one or more lease records from the Dynamic Host Configuration Protocol (DHCP) server service.

## SYNTAX

### ScopeId (Default)
```
Get-DhcpServerv4Lease [-ScopeId] <IPAddress> [-AllLeases] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

### IPAddress
```
Get-DhcpServerv4Lease [[-ScopeId] <IPAddress>] [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-ThrottleLimit <Int32>] [-BadLeases]
```

### ClientId
```
Get-DhcpServerv4Lease [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-ThrottleLimit <Int32>]
 -IPAddress <IPAddress[]>
```

### BadLeases
```
Get-DhcpServerv4Lease [-ScopeId] <IPAddress> [-ClientId] <String[]> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DhcpServerv4Lease** cmdlet gets one or more lease records from the Dynamic Host Configuration Protocol (DHCP) server service.

If you specify the *ScopeId* parameter, the active leases from the specified scope are returned.
To get all kinds of leases including Active, Offered, Declined, and Expired, the *AllLeases* parameter must be specified.

If you specify the *IPAddress* parameter, the lease records for the specified IP address are returned.

If you specify the *ClientId* and *ScopeId* parameters, the leases for the specified *ClientId* parameter values in the specified scope are returned.

If you specify the *BadLeases* and *ScopeId* parameters, all of the bad lease records for the specified scope are returned.

If you specify the *BadLeases* parameter without the *ScopeId* parameter, all of the bad lease records from the DHCP server service are returned.

## EXAMPLES

### Example 1: Get all active leases in a scope
```powershell
PS C:\> Get-DhcpServerv4Lease -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0
```

This example gets all the active IPv4 address leases from the DHCPv4 scope 10.10.10.0.

### Example 2: Get leases for specified addresses
```powershell
PS C:\> Get-DhcpServerv4Lease -ComputerName "dhcpserver.contoso.com" -IPAddress 10.10.10.10,10.20.20.20
```

This example gets the IP address lease information for the IPv4 addresses 10.10.10.10 and 10.20.20.20.

### Example 3: Get declined leases
```powershell
PS C:\> Get-DhcpServerv4Lease -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -BadLeases
```

This example gets all the bad, or declined, IPv4 address leases from the DHCPv4 scope 10.10.10.0.

### Example 4: Get leases for specified clients
```powershell
PS C:\> Get-DhcpServerv4Lease -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -ClientId "F0-DE-F1-7A-00-5E", "00-24-D7-C5-25-B0"
```

This example gets the IPv4 address leases from the DHCPv4 scope 10.10.10.0 for the clients identified by the client IDs F0-DE-F1-7A-00-5E and 00-24-D7-C5-25-B0.

### Example 5: Get all leases in a scope
```powershell
PS C:\> Get-DhcpServerv4Lease -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -AllLeases
```

This example gets all of the types of IPv4 address leases including Active, Declined, and Expired from the DHCPv4 scope 10.10.10.0.

### Example 6: Get active leases from all scopes on a computer
```powershell
PS C:\> Get-DhcpServerv4Scope -ComputerName "dhcpserver.contoso.com" | Get-DhcpServerv4Lease -ComputerName "dhcpserver.contoso.com"
```

This example gets all of the active IP address leases from all of the scopes on the DHCP server service that runs on the computer named dhcpserver.contoso.com.
The **Get-DhcpServerv4Scope** cmdlet returns the scope objects and pipes the objects into this cmdlet which returns the active address lease objects from all the scopes.

## PARAMETERS

### -AllLeases
Specifies that all of the IPv4 address leases regardless of address state are returned. 

If not specified, then only active leases are returned.

```yaml
Type: SwitchParameter
Parameter Sets: ScopeId (Default)
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

### -BadLeases
Specifies that only bad leases are returned.
If an IP address lease is declined by the client because of a conflict with another client, then the lease record is marked as bad, or declined, by the DHCP server service. 

An IP address lease in this state is not offered to any client until expiry of a timer, which is 10 minutes.

```yaml
Type: SwitchParameter
Parameter Sets: IPAddress
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Specifies the client identifier (ID) for which the IP address lease record is to be retrieved.

```yaml
Type: String[]
Parameter Sets: BadLeases
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the DHCP server service.

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
Specifies the IP address for which the lease record is to be retrieved.

```yaml
Type: IPAddress[]
Parameter Sets: ClientId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScopeId
Specifies the scope ID, in IPv4 address format from which the IPv4 address leases are being retrieved.

```yaml
Type: IPAddress
Parameter Sets: ScopeId (Default), BadLeases
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: IPAddress
Parameter Sets: IPAddress
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

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Lease[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4Lease](./Add-DhcpServerv4Lease.md)

[Get-DhcpServerv4Scope](./Get-DhcpServerv4Scope.md)

[Remove-DhcpServerv4Lease](./Remove-DhcpServerv4Lease.md)

