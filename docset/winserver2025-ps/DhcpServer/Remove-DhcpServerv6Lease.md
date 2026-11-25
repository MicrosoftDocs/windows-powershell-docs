---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerv6Lease_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/remove-dhcpserverv6lease?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DhcpServerv6Lease
---

# Remove-DhcpServerv6Lease

## SYNOPSIS
Deletes IPv6 lease records from the DHCP server service.

## SYNTAX

### IPAddress (Default)
```
Remove-DhcpServerv6Lease [-ComputerName <String>] [-PassThru] -IPAddress <IPAddress[]>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Prefix
```
Remove-DhcpServerv6Lease [-ComputerName <String>] [-PassThru] [-Prefix] <IPAddress>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DhcpServerv6Lease** cmdlet deletes one or more IPv6 lease records from the Dynamic Host Configuration Protocol (DHCP) server service.
If the *Prefix* parameter is specified, this cmdlet removes all of the leases for the specified prefix.
If the *IPAddress* parameter is specified, this cmdlet deletes the specified leases.

## EXAMPLES

### Example 1: Delete all leases in a scope
```
PS C:\> Remove-DhcpServerv6Lease -ComputerName "dhcpserver.contoso.com" -Prefix 2001:4898:7020:1020::
```

This example deletes all of the IP address leases in the scope 2001:4898:7020:1020:: from the DHCP server service that runs on the computer named dhcpserver.contoso.com.

### Example 2: Delete leases for specified addresses
```
PS C:\> Remove-DhcpServerv6Lease -ComputerName "dhcpserver.contoso.com" -IPAddress 2001:4898:7020:1020::10,2001:4898:7020:1030::20
```

This example deletes the IP address leases for 2001:4898:7020:1020::10 and 2001:4898:7020:1030::20 from the DHCP server service that runs on the computer named dhcpserver.contoso.com.

### Example 3: Delete leases for a scope by using the pipeline
```
PS C:\> Get-DhcpServerv6Lease -ComputerName "dhcpserver.contoso.com" -Prefix 2001:4898:7020:1020:: | Remove-DhcpServerv6Lease -ComputerName "dhcpserver.contoso.com"
```

This example deletes all of the IPv6 address leases from the scope 2001:4898:7020:1020::.
The **Get-DhcpServerv6Lease** cmdlet returns the IP address lease objects and pipes the objects into this cmdlet, which deletes each of the address leases.

### Example 4: Delete all the leases in all scopes on a computer
```
PS C:\> Get-DhcpServerv6Scope -ComputerName "dhcpserver.contoso.com" | Remove-DhcpServerv6Lease -ComputerName "dhcpserver.contoso.com"
```

The above command deletes all IPv6 address leases from all the DHCPv6 scopes.
The cmdlet Get-DhcpServerv6Scope cmdlet returns the DHCPv6 scope objects and pipe the objects into this cmdlet, which deletes each of the address leases passed through the pipeline.

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
Specifies one or more IPv6 addresses for which the lease records are deleted from the DHCP server service.

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

### -Prefix
Specifies the IPv6 subnet prefix of the scope from which the leases are deleted.

```yaml
Type: IPAddress
Parameter Sets: Prefix
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

[Get-DhcpServerv6Lease](./Get-DhcpServerv6Lease.md)

[Get-DhcpServerv6Scope](./Get-DhcpServerv6Scope.md)

