---
external help file: DhcpServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 29C269A1-A138-4E9C-9042-9E96CB71E75C
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Get-DhcpServerv6ScopeStatistics

## SYNOPSIS
Gets the IPv6 prefix statistics that correspond to the IPv6 prefix specified for a Dynamic Host Configuration Protocol (DHCP) server service.

## SYNTAX

```
Get-DhcpServerv6ScopeStatistics [[-Prefix] <IPAddress[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DhcpServerv6ScopeStatistics** cmdlet gets the scope statistics that correspond to the specified IPv6 prefix present on a Dynamic Host Configuration Protocol (DHCP) server service.
If the **Prefix** parameter is not specified, then this cmdlet returns statistics for all of the IPv6 prefixes.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DhcpServerv6ScopeStatistics -ComputerName dhcpserver.contoso.com
```

This example gets the scope statistics for all of the DHCPv6 scopes on the DHCP server service running on the computer named dhcpserver.contoso.com.

### EXAMPLE 2
```
PS C:\>Get-DhcpServerv6ScopeStatistics -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020::
```

This example gets the scope statistics for specified DHCPv6 scope.

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

### -Prefix
Specifies the IPv6 prefixes of the scopes for which the statistics are requested.

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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6ScopeStatistics[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv6Scope](./Add-DhcpServerv6Scope.md)

[Get-DhcpServerv6Scope](./Get-DhcpServerv6Scope.md)

[Remove-DhcpServerv6Scope](./Remove-DhcpServerv6Scope.md)

[Set-DhcpServerv6Scope](./Set-DhcpServerv6Scope.md)

