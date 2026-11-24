---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerv6FreeIPAddress_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv6freeipaddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DhcpServerv6FreeIPAddress
---

# Get-DhcpServerv6FreeIPAddress

## SYNOPSIS
Gets one or more free or unassigned IPv6 addresses from the specified scope.

## SYNTAX

```
Get-DhcpServerv6FreeIPAddress [-ComputerName <String>] [-Prefix] <IPAddress> [[-NumAddress] <UInt32>]
 [-StartAddress <IPAddress>] [-EndAddress <IPAddress>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DhcpServerv6FreeIPAddress** cmdlet gets one or more free IPv6 addresses from the specified scope.

If you specify the *NumAddress* parameter, the requested number of free IPv6 addresses are returned.
If you do not specify the *NumAddress* parameter, a single free IPv6 address is returned.
The maximum number of free IPv6 addresses returned is capped at 1024.

If you specify the *StartAddress* parameter and not the *EndAddress* parameter, the free IPv6 addresses starting from the *StartAddress* parameter value through the ending of the IPv6 address range of the scope are returned.

If you specify the *EndAddress* parameter and not the *StartAddress* parameter, the free IPv6 addresses starting from the start of the IPv6 address range of the scope through the *EndAddress* parameter value are returned.

If you specify both the *StartAddress* and *EndAddress* parameters, the free IPv6 addresses between the specified *StartAddress* and *EndAddress* parameter values are returned.

The exclusion address ranges, reservations, active, offered and bad, or declined, leases are excluded while returning free IPv6 addresses.

The IPv6 address ranges associated with a policy are included while returning free IPv6 addresses.

The IPv6 addresses which are in expired, or doomed, state are included while returning free IPv6 addresses.

If the requested number of free IPv6 addresses could not be found, a warning is displayed.

## EXAMPLES

### Example 1: Get a free address
```
PS C:\> Get-DhcpServerv6FreeIPAddress -ComputerName "dhcpserver.contoso.com" -Prefix 2001:4898:7020:1020::
```

This example gets a free IPv6 address from the specified scope.

### Example 2: Get ten free addresses
```
PS C:\> Get-DhcpServerv6FreeIPAddress -ComputerName "dhcpserver.contoso.com" -Prefix 2001:4898:7020:1020:: -NumAddress 10
```

This example gets a list of ten free IPv6 addresses from the specified scope.

### Example 3: Get a free address from a range
```
PS C:\> Get-DhcpServerv6FreeIPAddress -ComputerName "dhcpserver.contoso.com" -Prefix 2001:4898:7020:1020:: -StartAddress 2001:4898:7020:1020::10 -EndAddress 2001:4898:7020:1020::50
```

This example gets a free IPv6 address from the specified scope in the IP address range from 2001:4898:7020:1020::10 through 2001:4898:7020:1020::50.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.

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
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndAddress
Specifies the ending IPv6 address of the range from which the free IPv6 addresses are returned.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumAddress
Specifies the number of free IPv6 addresses requested.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prefix
Specifies the IPv6 subnet prefix of the scope from which one or more free IPv6 addresses are requested.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartAddress
Specifies the starting IPv6 address of the range from which the free IPv6 addresses are returned.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### System.String[]

## NOTES

## RELATED LINKS

[Get-DhcpServerv4FreeIPAddress](./Get-DhcpServerv4FreeIPAddress.md)
