---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerV4Reservation_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/remove-dhcpserverv4reservation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DhcpServerv4Reservation
---

# Remove-DhcpServerv4Reservation

## SYNOPSIS
Deletes the IPv4 reservation from the specified scope.

## SYNTAX

### IPAddress (Default)
```
Remove-DhcpServerv4Reservation [-ComputerName <String>] [-PassThru] -IPAddress <IPAddress[]>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ScopeId
```
Remove-DhcpServerv4Reservation [-ScopeId] <IPAddress> [-ComputerName <String>] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ClientId
```
Remove-DhcpServerv4Reservation [-ScopeId] <IPAddress> [-ClientId] <String[]> [-ComputerName <String>]
 [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DhcpServerv4Reservation** cmdlet deletes the IPv4 reservation from the specified scope.
If the *ScopeId* parameter is specified, all of the reservations from the scope are deleted.
If you specify the *IPAddress* or *ClientId* parameter, one or more specific reservations identified by IP addresses or client identifiers (IDs) are deleted.

## EXAMPLES

### Example 1: Delete all reservations in a scope
```
PS C:\> Remove-DhcpServerv4Reservation -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0
```

This example deletes all of the reservations in the specified scope.

### Example 2: Delete specified reservations
```
PS C:\> Remove-DhcpServerv4Reservation -ComputerName "dhcpserver.contoso.com" -IPAddress 10.10.10.5, 10.10.10.6
```

This example deletes the specified reservations from the DHCP server service.

### Example 3: Delete reservations for a specified client
```
PS C:\> Remove-DhcpServerv4Reservation -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -ClientId "F0-DE-F1-7A-00-5E"
```

This example deletes the specified reservation identified by client ID from the DHCP server service.
For computers that run the Windows operating system, the MAC address is used as a client identifier.

### Example 4: Delete reserved IP addresses from all scopes
```
PS C:\> Get-DhcpServerv4Scope -ComputerName "dhcpserver.contoso.com" | Remove-DhcpServerv4Reservation -ComputerName "dhcpserver.contoso.com"
```

This example deletes all of the reserved IP addresses from all of the scopes on the DHCP server service that runs on the computer named dhcpserver.contoso.com.
The **Get-DhcpServerv4Scope** cmdlet returns all of the scope objects and pipes the objects into this cmdlet, which deletes the reservations from each scope passed in through the pipeline.

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

### -ClientId
Specifies one or more client IDs for one of more reservations which are deleted.
For Windows clients, the MAC address is used as a client identifier.

```yaml
Type: String[]
Parameter Sets: ClientId
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Specifies one or more IPv4 addresses for one or more reservations which are deleted.

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

### -ScopeId
Specifies the scope ID, in IPv4 address format, from which the reservations are deleted.

```yaml
Type: IPAddress
Parameter Sets: ScopeId, ClientId
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Reservation
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Reservation[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4Reservation](./Add-DhcpServerv4Reservation.md)

[Get-DhcpServerv4Reservation](./Get-DhcpServerv4Reservation.md)

[Get-DhcpServerv4Scope](./Get-DhcpServerv4Scope.md)

[Set-DhcpServerv4Reservation](./Set-DhcpServerv4Reservation.md)

