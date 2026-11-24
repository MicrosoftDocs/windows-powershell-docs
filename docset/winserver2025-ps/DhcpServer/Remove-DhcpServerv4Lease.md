---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerv4Lease_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/remove-dhcpserverv4lease?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DhcpServerv4Lease
---

# Remove-DhcpServerv4Lease

## SYNOPSIS
Deletes IPv4 address lease records from the DHCP server service.

## SYNTAX

### IPAddress (Default)
```
Remove-DhcpServerv4Lease [-PassThru] [-ComputerName <String>] -IPAddress <IPAddress[]>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ScopeId
```
Remove-DhcpServerv4Lease [-PassThru] [-ComputerName <String>] [-ScopeId] <IPAddress>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ClientId
```
Remove-DhcpServerv4Lease [-PassThru] [-ComputerName <String>] [-ScopeId] <IPAddress> [-ClientId] <String[]>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BadLeases
```
Remove-DhcpServerv4Lease [-PassThru] [-ComputerName <String>] [-BadLeases] [[-ScopeId] <IPAddress>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DhcpServerv4Lease** cmdlet deletes one or more IPv4 lease records from the Dynamic Host Configuration Protocol (DHCP) server service.

If you specify the *ScopeId* parameter, all of the leases for the specified scope are deleted.

If you specify the *IPAddress* parameter, the leases for clients identified by one or more specified IP addresses are deleted.
If you specify the *ClientId* and the *ScopeId* parameters, the lease for the specified client identifier (ID) from the specified scope is deleted.

If you specify the *BadLeases* and the *ScopeId* parameters, this cmdlet removes all of the bad lease records for the specified scope.

If you specify the *BadLeases* parameter without the *ScopeId* parameter, this cmdlet removes all of the bad leases from all of the scopes on the DHCP server service.

## EXAMPLES

### Example 1: Delete leases in a scope
```
PS C:\> Remove-DhcpServerv4Lease -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0
```

This example deletes all of the IPv4 address leases in the scope 10.10.10.0 from the DHCP server service that runs on the computer named dhcpserver.contoso.com.

### Example 2: Delete leases for multiple addresses
```
PS C:\> Remove-DhcpServerv4Lease -ComputerName "dhcpserver.contoso.com" -IPAddress 10.10.10.10,20.20.20.20
```

This example deletes the IPv4 address leases for 10.10.10.10 and 10.20.20.20 from the DHCP server service that runs on the computer named dhcpserver.contoso.com.

### Example 3: Delete leases for specified clients
```
PS C:\> Remove-DhcpServerv4Lease -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -ClientId "F0-DE-F1-7A-00-5E","00-24-D7-C5-25-B0"
```

This example deletes the IPv4 address leases from the DHCPv4 scope 10.10.10.0 for the clients identified by the client IDs F0-DE-F1-7A-00-5E and 00-24-D7-C5-25-B0.

### Example 4: Delete declined leases in a scope
```
PS C:\> Remove-DhcpServerv4Lease -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -BadLeases
```

This example deletes all of the bad, or declined, IPv4 address leases in the scope 10.10.10.0 from the DHCP server service that runs on the computer named dhcpserver.contoso.com.

### Example 5: Delete declined leases by using the pipeline
```
PS C:\> Get-DhcpServerv4Scope -ComputerName "dhcpserver.contoso.com" | Get-DhcpServerv4Lease -ComputerName "dhcpserver.contoso.com" -BadLeases | Remove-DhcpServerv4Lease -ComputerName "dhcpserver.contoso.com" -BadLeases
```

This example deletes all of the bad, or declined, IPv4 address leases from all of the scopes on the DHCP server service that runs on the computer named dhcpserver.contoso.com.
The **Get-DhcpServerv4Scope** cmdlet returns all of the scope objects and the scope objects are piped into the **Get-DhcpServerv4Lease** cmdlet.
The **Get-DhcpServerv4Lease** cmdlet returns the bad address lease objects from all the scopes and the bad address lease objects are piped into this cmdlet, which deletes all of the bad address leases.

### Example 6: Delete leases in a scope by using the pipeline
```
PS C:\> Get-DhcpServerv4Lease -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -AllLeases | Remove-DhcpServerv4Lease -ComputerName "dhcpserver.contoso.com"
```

This example deletes all IPv4 address leases from the scope 10.10.10.0.
The command works by pipelining from the first cmdlet Get-DhcpServerv4Lease cmdlet returns the IPv4 address lease objects and the IPv4 address lease objects are piped into this cmdlet, which deletes the bad address leases.

### Example 7: Delete all the leases on all the scopes on a computer
```
PS C:\> Get-DhcpServerv4Scope -ComputerName "dhcpserver.contoso.com" | Remove-DhcpServerv4Lease -ComputerName "dhcpserver.contoso.com"
```

This example deletes all of the IPv4 address leases from all of the DHCPv4 scopes on the DHCP server service that runs on the computer named dhcpserver.contoso.com.
The **Get-DhcpServerv4Scope** cmdlet returns the DHCPv4 scope objects and the DHCPv4 scope objects are piped into this cmdlet, which deletes each of the address leases.

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

### -BadLeases
Specifies that all of the bad IP address leases are deleted.
An IPv4 address lease which is declined by a client because of an IPv4 address conflict is marked as bad by the DHCP server service.

```yaml
Type: SwitchParameter
Parameter Sets: BadLeases
Aliases:

Required: True
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
Specifies the client ID whose IPv4 address lease is to be deleted.
Windows clients use the MAC address as the client ID.

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
Specifies one or more IP addresses for which the lease records are deleted.

```yaml
Type: IPAddress[]
Parameter Sets: IPAddress
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
Parameter Sets: ScopeId, ClientId
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: IPAddress
Parameter Sets: BadLeases
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

