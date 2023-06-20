---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://learn.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv4dnssetting?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-DhcpServerv4DnsSetting

## SYNOPSIS
Gets the DNS settings configured on the Dynamic Host Configuration Protocol (DHCP) server service for a specific scope, reservation, or server level.

## SYNTAX

```
Get-DhcpServerv4DnsSetting [[-ScopeId] <IPAddress>] [[-IPAddress] <IPAddress>] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DhcpServerv4DnsSetting** cmdlet gets the DNS settings configured on the Dynamic Host Configuration Protocol (DHCP) server service for a specific scope, reservation, or server level.

If neither the **ScopeId** nor **IPAddress** parameter is specified, then DNS update settings from server level are returned.

The **ScopeId** and **IPAddress** parameters cannot both be specified.

This cmdlet gets the effective DNS setting at the specified level such as reservation, scope, or server.
If the DNS setting value is not configured at the specified level, then the DNS settings from the level above will be fetched if configured.
If the DNS setting is not specified at the server level, then the default behavior of the DHCP server service for DNS update is returned.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DhcpServerv4DnsSetting -ComputerName dhcpserver.contoso.com
```

This example gets the DHCPv4 server-level or server-wide DNS registration setting on the computer named dhcpserver.contoso.com.

### EXAMPLE 2
```
PS C:\>Get-DhcpServerv4DnsSetting -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0.
```

This example gets the DNS registration setting configured on the computer named dhcpserver.contoso.com for the scope 10.10.10.0.

### EXAMPLE 3
```
PS C:\>Get-DhcpServerv4DnsSetting -ComputerName dhcpserver.contoso.com -IPAddress 10.10.10.10
```

This example gets the DNS registration setting configured on the computer named dhcpserver.contoso.com for the reserved IP address 10.10.10.10.

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
Specifies the DNS name, or IPv4 or IP6 address, of the target computer running the DHCP server service.

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
Specifies the IP address of the reservation for which the DNS update settings are to be retrieved.

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

### -ScopeId
Specifies the scope identifier (ID), in IPv4 address format, for which the DNS update settings are to be retrieved.

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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Reservation
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4DnsSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Set-DhcpServerv4DnsSetting](./Set-DhcpServerv4DnsSetting.md)

