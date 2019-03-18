---
external help file: DhcpServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: AAC6BD13-2DF9-4DC8-826C-D9EEEDAD2C50
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Remove-DhcpServerv4Lease

## SYNOPSIS
Deletes the specified IPv4 address lease record from the Dynamic Host Configuration Protocol (DHCP) server service.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-DhcpServerv4Lease [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru]
 [-ThrottleLimit <Int32>] -IPAddress <IPAddress[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-DhcpServerv4Lease [-ScopeId] <IPAddress> [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Remove-DhcpServerv4Lease [-ScopeId] <IPAddress> [-ClientId] <String[]> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Remove-DhcpServerv4Lease [[-ScopeId] <IPAddress>] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>] [-BadLeases] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-DhcpServerv4Lease** cmdlet deletes one or more IPv4 lease records from the Dynamic Host Configuration Protocol (DHCP) server service.

If the **ScopeId** parameter is specified, then all of the leases for the specified scope are deleted.

If the **IPAddress** parameter is specified, then the leases for clients identified by one or more specified IP addresses are deleted.
If the **ClientId** and the **ScopeId** parameter is specified, then the lease for the specified client identifier (ID) from the specified scope is deleted.

If the **BadLeases** and the **ScopeId** parameters are specified, then this cmdlet removes all of the bad lease records for the specified scope.

If the **BadLeases** parameter is specified without the **ScopeId** parameter, then this cmdlet removes all of the bad leases from all of the scopes on the DHCP server service.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-DhcpServerv4Lease -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0
```

This example deletes all of the IPv4 address leases inside of the scope 10.10.10.0 from the DHCP server service running on the computer named dhcpserver.contoso.com.

### EXAMPLE 2
```
PS C:\>Remove-DhcpServerv4Lease -ComputerName dhcpserver.contoso.com -IPAddress 10.10.10.10,20.20.20.20
```

This example deletes the IPv4 address leases for 10.10.10.10 and 20.20.20.20 from the DHCP server service running on the computer named dhcpserver.contoso.com.

### EXAMPLE 3
```
PS C:\>Remove-DhcpServerv4Lease -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -ClientId F0-DE-F1-7A-00-5E,00-24-D7-C5-25-B0
```

This example deletes the IPv4 address leases from the DHCPv4 scope 10.10.10.0 for the clients identified by the client IDs F0-DE-F1-7A-00-5E and 00-24-D7-C5-25-B0.

### EXAMPLE 4
```
PS C:\>Remove-DhcpServerv4Lease -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -BadLeases
```

This example deletes all of the bad, or declined, IPv4 address leases inside of the scope 10.10.10.0 from the DHCP server service running on the computer named dhcpserver.contoso.com.

### EXAMPLE 5
```
PS C:\>Get-DhcpServerv4Scope -ComputerName dhcpserver.contoso.com | Get-DhcpServerv4Lease -ComputerName dhcpserver.contoso.com -BadLeases | Remove-DhcpServerv4Lease -ComputerName dhcpserver.contoso.com -BadLeases
```

This example deletes all of the bad, or declined, IPv4 address leases from all of the scopes on the DHCP server service running on the computer named dhcpserver.contoso.com.
The Get-DhcpServerv4Scope cmdlet returns all of the scope objects and the scope objects are piped into the Get-DhcpServerv4Lease cmdlet.
The Get-DhcpServerv4Lease cmdlet returns the bad address lease objects from all the scopes and the bad address lease objects are piped into this cmdlet, which deletes all of the bad address leases.

### EXAMPLE 6
```
PS C:\>Get-DhcpServerv4Lease -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -AllLeases | Remove-DhcpServerv4Lease -ComputerName dhcpserver.contoso.com
```

This example deletes all IPv4 address leases from the scope 10.10.10.0.
The command works by pipelining from the first cmdlet Get-DhcpServerv4Lease cmdlet returns the IPv4 address lease objects and the IPv4 address lease objects are piped into this cmdlet, which deletes the bad address leases.

### EXAMPLE 7
```
PS C:\>Get-DhcpServerv4Scope -ComputerName dhcpserver.contoso.com | Remove-DhcpServerv4Lease -ComputerName dhcpserver.contoso.com
```

This example deletes all of the IPv4 address leases from all of the DHCPv4 scopes on the DHCP server service running on the computer named dhcpserver.contoso.com.
The Get-DhcpServerv4Scope cmdlet returns the DHCPv4 scope objects and the DHCPv4 scope objects are piped into this cmdlet, which deletes each of the address leases.

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

### -BadLeases
Specifies that all of the bad IP address leases are deleted.
An IPv4 address lease which is declined by a client because of an IPv4 address conflict is marked as bad by the DHCP server service.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_4
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
Specifies the client ID whose IPv4 address lease is to be deleted.
Windows clients use the MAC address as the client ID.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
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
Specifies one or more IP addresses for which the lease records are deleted.

```yaml
Type: IPAddress[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
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
Specifies the scope ID, in IPv4 address format, from which the IP address leases are deleted.

```yaml
Type: IPAddress
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: IPAddress
Parameter Sets: UNNAMED_PARAMETER_SET_4
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Lease[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4Lease](./Add-DhcpServerv4Lease.md)

[Get-DhcpServerv4Lease](./Get-DhcpServerv4Lease.md)

[Get-DhcpServerv4Scope](./Get-DhcpServerv4Scope.md)

