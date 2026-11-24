---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerV6Reservation_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/remove-dhcpserverv6reservation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DhcpServerv6Reservation
---

# Remove-DhcpServerv6Reservation

## SYNOPSIS
Deletes IPv6 reservations from the specified scope.

## SYNTAX

### IPAddress (Default)
```
Remove-DhcpServerv6Reservation [-ComputerName <String>] -IPAddress <IPAddress[]> [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Prefix
```
Remove-DhcpServerv6Reservation [-ComputerName <String>] [-PassThru] [-Prefix] <IPAddress>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DhcpServerv6Reservation** cmdlet deletes one or more IPv6 reservations from the specified scope.
If you specify the *Prefix* parameter, all of the reservations from the scope are removed.
If you specify the *IPAddress* parameter, one or more specified reservations are removed.

## EXAMPLES

### Example 1: Delete a reservation
```
PS C:\> Remove-DhcpServerv6Reservation -ComputerName "dhcpserver.contoso.com" -IPAddress 2001:4898:7020:1020::1,2001:4898:7020:1020::2
```

This example deletes the reservation for the specified IPv6 addresses.

### Example 2: Delete all reservations for a scope
```
PS C:\> Remove-DhcpServerv6Reservation -ComputerName "dhcpserver.contoso.com" -Prefix 2001:4898:7020:1020::
```

This example deletes all of the reservations from the specified IPv6 scope.

### Example 3: Delete all reservations for all scopes
```
PS C:\> Get-DhcpServerv6Scope -ComputerName "dhcpserver.contoso.com" | Remove-DhcpServerv6Reservation -ComputerName "dhcpserver.contoso.com"
```

This example deletes all of the reserved IP addresses from all of the DHCPv6 scopes on the DHCP server service that runs on the computer named dhcpserver.contoso.com.
The **Get-DhcpServerv6Scope** cmdlet returns all of the scope objects and pipes the objects into this cmdlet, which deletes the reservations from each of the scopes passed through the pipeline.

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
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer that runs the Dynamic Host Configuration Protocol (DHCP) server service.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn, ReservationServer

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
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddress
Specifies one or more IPv6 addresses of the reservations that are deleted.

```yaml
Type: IPAddress[]
Parameter Sets: IPAddress
Aliases: ReservedIP

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
Specifies the IPv6 subnet prefix of the scope from which one or more reservations are deleted.

```yaml
Type: IPAddress
Parameter Sets: Prefix
Aliases: ReservationScopeID

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

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

