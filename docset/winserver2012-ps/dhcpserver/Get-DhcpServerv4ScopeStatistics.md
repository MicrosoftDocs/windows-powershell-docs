---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://docs.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv4scopestatistics?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-DhcpServerv4ScopeStatistics

## SYNOPSIS
Gets the IPv4 scope statistics corresponding to the IPv4 scope identifiers (IDs) specified for a Dynamic Host Configuration Protocol (DHCP) server service.

## SYNTAX

```
Get-DhcpServerv4ScopeStatistics [[-ScopeId] <IPAddress[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-Failover] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DhcpServerv4ScopeStatistics** cmdlet gets the scope statistics corresponding to the IPv4 scope identifiers (IDs) specified for a Dynamic Host Configuration Protocol (DHCP) server service.
If the **ScopeId** parameter is not specified, then this cmdlet gets the statistics for all of the IPv4 scopes.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DhcpServerv4ScopeStatistics -ComputerName dhcpServer.contoso.com
```

This example gets the scope statistics for all the scopes present on the specified DHCP server service.

### EXAMPLE 2
```
PS C:\>Get-DhcpServerv4ScopeStatistics -ComputerName dhcpServer.contoso.com -ScopeId 10.10.10.0
```

This example gets the scope statistics for the specified scope on the specified DHCP server service.

### EXAMPLE 3
```
PS C:\>Get-DhcpServerv4ScopeStatistics -ComputerName dhcpServer.contoso.com -ScopeId 10.10.10.0 -Failover
```

This example gets the scope statistics including those related to failover, if the scope is part of a failover relationship, for the specified scope on the specified DHCP server service.

### EXAMPLE 4
```
PS C:\>Get-DhcpServerv4ScopeStatistics -ComputerName dhcpServer.contoso.com -Failover
```

This example gets the scope statistics including those related to failover, if the scope is part of a failover relationship, for all of the scopes present on the specified DHCP server service.

### EXAMPLE 5
```
PS C:\>Get-DhcpServerv4ScopeStatistics -ComputerName dhcpServer.contoso.com | Where-Object -FilterScript { $_.PercentageInUse -Gt 80 }
```

This example gets the scope statistics for the scopes present on the specified DHCP server service, which have more than 80% of their IP address range exhausted.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -Failover
Specifies that, if the scope is configured for failover, the failover related scope statistics are returned as part of the scope statistics.

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
Specifies the scope IDs, in IPv4 address format, for which the statistics are returned.

```yaml
Type: IPAddress[]
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

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4ScopeStatistics[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkId=113423)

[Add-DhcpServerv4Scope](./Add-DhcpServerv4Scope.md)

[Get-DhcpServerv4Scope](./Get-DhcpServerv4Scope.md)

[Remove-DhcpServerv4Scope](./Remove-DhcpServerv4Scope.md)

[Set-DhcpServerv4Scope](./Set-DhcpServerv4Scope.md)

