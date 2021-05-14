---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://docs.microsoft.com/powershell/module/dhcpserver/remove-dhcpserverv6reservation?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-DhcpServerv6Reservation

## SYNOPSIS
Deletes one or more IPv6 reservations from the specified scope.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-DhcpServerv6Reservation [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru]
 [-ThrottleLimit <Int32>] -IPAddress <IPAddress[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-DhcpServerv6Reservation [-Prefix] <IPAddress> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-DhcpServerv6Reservation** cmdlet deletes one or more IPv6 reservations from the specified scope.
If the **Prefix** parameter is specified, then all of the reservations from the scope will be removed.
If the **IPAddress** parameter is specified, then one or more specified reservations are deleted.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-DhcpServerv6Reservation -ComputerName dhcpserver.contoso.com -IPAddress 2001:4898:7020:1020::1,2001:4898:7020:1020::2
```

This example deletes the reservation for the specified IPv6 addresses.

### EXAMPLE 2
```
PS C:\>Remove-DhcpServerv6Reservation -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020::
```

This example deletes all of the reservations from the specified IPv6 scope.

### EXAMPLE 3
```
PS C:\>Get-DhcpServerv6Scope -ComputerName dhcpserver.contoso.com | Remove-DhcpServerv6Reservation -ComputerName dhcpserver.contoso.com
```

This example deletes all of the reserved IP addresses from all of the DHCPv6 scopes on the DHCP server service running on the computer named dhcpserver.contoso.com.
The Get-DhcpServerv6Scope cmdlet returns all of the scope objects and pipes the objects into this cmdlet, which deletes the reservations from each of the scopes passed through the pipeline.

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
Specifies one or more IPv6 addresses of the reservations being deleted.

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

### -Prefix
Specifies the IPv6 subnet prefix of the scope from which one or more reservations are being deleted.

```yaml
Type: IPAddress
Parameter Sets: UNNAMED_PARAMETER_SET_2
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Reservation
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Reservation[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv6Reservation](./Add-DhcpServerv6Reservation.md)

[Get-DhcpServerv6Reservation](./Get-DhcpServerv6Reservation.md)

[Get-DhcpServerv6Scope](./Get-DhcpServerv6Scope.md)

[Set-DhcpServerv6Reservation](./Set-DhcpServerv6Reservation.md)

