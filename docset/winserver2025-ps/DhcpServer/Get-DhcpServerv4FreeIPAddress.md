---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerv4FreeIPAddress_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv4freeipaddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DhcpServerv4FreeIPAddress
---

# Get-DhcpServerv4FreeIPAddress

## SYNOPSIS
Gets one or more free or unassigned IPv4 Addresses from the specified scope.

## SYNTAX

```
Get-DhcpServerv4FreeIPAddress [-ComputerName <String>] [-ScopeId] <IPAddress> [[-NumAddress] <UInt32>]
 [-StartAddress <IPAddress>] [-EndAddress <IPAddress>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
This **Get-DhcpServerv4FreeIPAddress** cmdlet gets one or more free IP addresses from the specified scope.

If you specify the *NumAddress* parameter, the requested number of free IPv4 addresses are returned.
If you do not specify the *NumAddress* parameter, a single free IP address is returned.
The maximum number of free IP addresses returned is capped at 1024.

If you specify the *StartAddress* parameter and not the *EndAddress* parameter, the free IP addresses starting from the *StartAddress* parameter value through the end of the IP address range of the scope are returned.

If you specify the *EndAddress* parameter and not the *StartAddress* parameter, the free IP addresses starting from the start of the IP address range of the scope through the *EndAddress* parameter value are returned.

If you specify both the *StartAddress* and *EndAddress* parameters, the free IP addresses between the *StartAddress* and *EndAddress* parameter values are returned.

The exclusion address ranges, reservations, active, offered, and bad, or declined, leases are excluded while returning the free IP addresses.

The IP address ranges associated with a policy are included while returning the free IP addresses.

The IP addresses which are in expired, or doomed, state will be included while returning the free IP addresses.

If the requested number of free IP addresses could not be found, this cmdlet displays a warning.

## EXAMPLES

### Example 1: Get a free address
```
PS C:\> Get-DhcpServerv4FreeIPAddress -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0
```

This example gets a free IPv4 addresses from the specified scope.

### Example 2: Get ten free addresses
```
PS C:\> Get-DhcpServerv4FreeIPAddress -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -NumAddress 10
```

This example gets a list of ten free IPv4 addresses from the specified scope.

### Example 3: Get a free address from a range
```
PS C:\> Get-DhcpServerv4FreeIPAddress -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0 -StartAddress 10.10.10.10 -EndAddress 10.10.10.50
```

This example gets a free IPv4 address from the specified scope in the IP address range from 10.10.10.10 through 10.10.10.50.

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
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndAddress
Specifies the ending IP address of the range from which the free IP addresses are returned.

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
Specifies the number of free IP addresses requested.

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

### -ScopeId
Specifies the scope identifier (ID), in IPv4 address format, from which one or more free IP addresses are requested.

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
Specifies the starting IP address of the range from which the free IP addresses are returned.

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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### System.String[]

## NOTES

## RELATED LINKS

[Get-DhcpServerv6FreeIPAddress](./Get-DhcpServerv6FreeIPAddress.md)
