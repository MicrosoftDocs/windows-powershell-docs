---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://learn.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv6lease?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-DhcpServerv6Lease

## SYNOPSIS
Gets one or more IPv6 lease records from the Dynamic Host Configuration Protocol (DHCP) server service.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-DhcpServerv6Lease [-Prefix] <IPAddress> [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-DhcpServerv6Lease [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-ThrottleLimit <Int32>]
 -IPAddress <IPAddress[]>
```

## DESCRIPTION
The **Get-DhcpServerv6Lease** cmdlet gets one or more IPv6 lease records from the Dynamic Host Configuration Protocol (DHCP) server service.

If the **Prefix** parameter is specified, then the leases in the specified scope are retrieved.

If the **IPAddress** parameter is specified, then the lease for the specified IPv6 address is retrieved.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DhcpServerv6Lease -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020::
```

This example gets all of the IP address lease from the DHCPv6 scope 2001:4898:7020:1020::.

### EXAMPLE 2
```
PS C:\>Get-DhcpServerv6Lease -ComputerName dhcpserver.contoso.com -IPAddress 2001:4898:7020:1020::10
```

This example gets the IP address lease information for the IPv6 address 2001:4898:7020:1020::10.

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
Specifies one or more IPv6 addresses for which the lease records are to be retrieved.

```yaml
Type: IPAddress[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Prefix
Specifies the subnet prefix of the scope from which the lease records are to be retrieved.

```yaml
Type: IPAddress
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Lease
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Lease[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv6Lease](./Add-DhcpServerv6Lease.md)

[Remove-DhcpServerv6Lease](./Remove-DhcpServerv6Lease.md)

