---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://learn.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv6dnssetting?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-DhcpServerv6DnsSetting

## SYNOPSIS
Gets the DNS settings configured on the Dynamic Host Configuration Protocol (DHCP) server service for a specific scope, reservation, or server-wide.

## SYNTAX

```
Get-DhcpServerv6DnsSetting [[-Prefix] <IPAddress>] [[-IPAddress] <IPAddress>] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DhcpServerv6DnsSetting** cmdlet gets the DNS settings configured on the Dynamic Host Configuration Protocol (DHCP) server service for a specific scope, reservation, or server-wide.

If neither the **Prefix** nor **IPAddress** parameter is specified, then the DNS settings at the server level are retrieved.
The **Prefix** and **IPAddress** parameters cannot both be specified.
If the **Prefix** or **IPAddress** parameter is specified, then this cmdlet gets the effective DNS setting at the specified level such as reservation, scope, or server.
If the DNS setting value is not configured at the specified level, then the DNS settings from the level above will be retrieved if configured.
If the DNS setting is not specified at the server level, then the default behavior of the DHCP server service such as DNS update is returned.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-DhcpServerv6DnsSetting -ComputerName dhcpserver.contoso.com
```

This example gets the DHCPv6 server-level or server-wide DNS registration setting.

### EXAMPLE 2
```
PS C:\> Get-DhcpServerv6DnsSetting -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020::
```

This example gets the DNS registration setting configured for the scope 2001:4898:7020:1020::.

### EXAMPLE 3
```
PS C:\> Get-DhcpServerv6DnsSetting -ComputerName dhcpserver.contoso.com -IPAddress 2001:4898:7020:1020::10
```

This example gets the DNS registration setting configured for the reserved IP address 2001:4898:7020:1020:10.

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

### -IPAddress
Specifies the IPv6 address of the reservation for which the DNS settings are to be retrieved.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Prefix
Specifies the subnet prefix of the IPv6 scope for which the DNS settings are to be retrieved.

```yaml
Type: IPAddress
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Reservation
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6DnsSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Set-DhcpServerv6DnsSetting](./Set-DhcpServerv6DnsSetting.md)

