---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerV4ScopeStatistics_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv4scopestatistics?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DhcpServerv4ScopeStatistics
---

# Get-DhcpServerv4ScopeStatistics

## SYNOPSIS
Gets the IPv4 scope statistics corresponding to the IPv4 scope IDs specified for a DHCP server service.

## SYNTAX

```
Get-DhcpServerv4ScopeStatistics [[-ScopeId] <IPAddress[]>] [-ComputerName <String>] [-Failover]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DhcpServerv4ScopeStatistics** cmdlet gets the scope statistics corresponding to the IPv4 scope identifiers (IDs) specified for a Dynamic Host Configuration Protocol (DHCP) server service.
If you do not specify the *ScopeId* parameter, this cmdlet gets the statistics for all of the IPv4 scopes.

## EXAMPLES

### Example 1: Get scope statistics for scopes on a DHCP server service
```
PS C:\> Get-DhcpServerv4ScopeStatistics -ComputerName "dhcpServer.contoso.com"
```

This example gets the scope statistics for the scopes on the specified DHCP server service.

### Example 2: Get scope statistics for a scope on a DHCP server service
```
PS C:\> Get-DhcpServerv4ScopeStatistics -ComputerName "dhcpServer.contoso.com" -ScopeId 10.10.10.0
```

This example gets the scope statistics for the specified scope on the specified DHCP server service.

### Example 3: Get scope statistics for a scope on a DHCP server service including failover
```
PS C:\> Get-DhcpServerv4ScopeStatistics -ComputerName "dhcpServer.contoso.com" -ScopeId 10.10.10.0 -Failover
```

This example gets the scope statistics including those related to failover, if the scope is part of a failover relationship, for the specified scope on the specified DHCP server service.

### Example 4: Get scope statistics for scopes on a DHCP server service including failover
```
PS C:\> Get-DhcpServerv4ScopeStatistics -ComputerName "dhcpServer.contoso.com" -Failover
```

This example gets the scope statistics including those related to failover, if the scope is part of a failover relationship, for all of the scopes on the specified DHCP server service.

### Example 5: Get statistics for scopes on a DHCP server service which have a portion of their IP address range exhausted
```
PS C:\> Get-DhcpServerv4ScopeStatistics -ComputerName "dhcpServer.contoso.com" | Where-Object -FilterScript { $_.PercentageInUse -Gt 80 }
```

This example gets the scope statistics for the scopes on the specified DHCP server service which have more than 80% of their IP address range exhausted.

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

### -ComputerName
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer that runs the DHCP server service.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

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

[Add-DhcpServerv4Scope](./Add-DhcpServerv4Scope.md)

[Get-DhcpServerv4Scope](./Get-DhcpServerv4Scope.md)

[Remove-DhcpServerv4Scope](./Remove-DhcpServerv4Scope.md)

[Set-DhcpServerv4Scope](./Set-DhcpServerv4Scope.md)

