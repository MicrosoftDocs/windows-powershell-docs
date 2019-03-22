---
external help file: DhcpServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: F76E414E-5562-4E98-9413-67D00AFE5878
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Get-DhcpServerv4Lease

## SYNOPSIS
Gets one or more lease records from the Dynamic Host Configuration Protocol (DHCP) server service.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-DhcpServerv4Lease [-ScopeId] <IPAddress> [-AllLeases] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-DhcpServerv4Lease [[-ScopeId] <IPAddress>] [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-ThrottleLimit <Int32>] [-BadLeases]
```

### UNNAMED_PARAMETER_SET_3
```
Get-DhcpServerv4Lease [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-ThrottleLimit <Int32>]
 -IPAddress <IPAddress[]>
```

### UNNAMED_PARAMETER_SET_4
```
Get-DhcpServerv4Lease [-ScopeId] <IPAddress> [-ClientId] <String[]> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DhcpServerv4Lease** cmdlet gets one or more lease records from the Dynamic Host Configuration Protocol (DHCP) server service.

If the **ScopeId** parameter is specified, then the active leases from the specified scope are returned.
To get all types of leases including Active, Offered, Declined, and Expired, then the **AllLeases** parameter must be specified.

If the **IPAddress** parameter is specified, then the lease records for the specified IP address are returned.

If the **ClientId** and **ScopeId** parameters are specified, then the leases for the specified **ClientId** parameter values in the specified scope are returned.

If the **BadLeases** and **ScopeId** parameters are specified, then all of the bad lease records for the specified scope are returned.

If the **BadLeases** parameter is specified without the **ScopeId** parameter, then all of the bad lease records from the DHCP server service are returned.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-DhcpServerv4Lease -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0
```

This example gets all the active IPv4 address leases from the DHCPv4 scopes 10.10.10.0.

### EXAMPLE 2
```
PS C:\> Get-DhcpServerv4Lease -ComputerName dhcpserver.contoso.com -IPAddress 10.10.10.10,20.20.20.20
```

This example gets the IP address lease information for the IPv4 addresses 10.10.10.10 and 20.20.20.20.

### EXAMPLE 3
```
PS C:\> Get-DhcpServerv4Lease -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -BadLeases
```

This example gets all the bad, or declined, IPv4 address leases from the DHCPv4 scope 10.10.10.0.

### EXAMPLE 4
```
PS C:\> Get-DhcpServerv4Lease -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -CliendId F0-DE-F1-7A-00-5E, 00-24-D7-C5-25-B0
```

This example gets the IPv4 address leases from the DHCPv4 scope 10.10.10.0 for the clients identified by the client IDs F0-DE-F1-7A-00-5E and 00-24-D7-C5-25-B0.

### EXAMPLE 5
```
PS C:\> Get-DhcpServerv4Lease -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -AllLeases
```

This example gets all of the types of IPv4 address leases including Active, Declined, and Expired from the DHCPv4 scope 10.10.10.0.

### EXAMPLE 6
```
PS C:\>Get-DhcpServerv4Scope -ComputerName dhcpserver.contoso.com | Get-DhcpServerv4Lease -ComputerName dhcpserver.contoso.com
```

This example gets all of the active IP address leases from all of the scopes on the DHCP server service running on the computer named dhcpserver.contoso.com.
The Get-DhcpServerv4Scope cmdlet returns the scope objects and pipes the objects into this cmdlet which returns the active address lease objects from all the scopes.

## PARAMETERS

### -AllLeases
Specifies that all of the IPv4 address leases regardless of address state are returned. 

If not specified, then only active leases are returned.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### -BadLeases
Specifies that only bad leases are returned.
If an IP address lease is declined by the client because of a conflict with another client, then the lease record is marked as bad, or declined, by the DHCP server service. 

An IP address lease in this state is not offered to any client until expiry of a timer, which is 10 minutes.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
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
Specifies the client identifier (ID) for which the IP address lease record is to be retrieved.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: IPAddress
Parameter Sets: UNNAMED_PARAMETER_SET_2
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

