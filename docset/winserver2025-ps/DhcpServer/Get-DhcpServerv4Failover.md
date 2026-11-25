---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerv4Failover_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv4failover?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DhcpServerv4Failover
---

# Get-DhcpServerv4Failover

## SYNOPSIS
Gets the failover relationships configured on the DHCP server service for the specific failover relationship name.

## SYNTAX

### Name (Default)
```
Get-DhcpServerv4Failover [-ComputerName <String>] [[-Name] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ScopeId
```
Get-DhcpServerv4Failover [-ComputerName <String>] -ScopeId <IPAddress[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DhcpServerv4Failover** cmdlet gets the failover relationships configured on the Dynamic Host Configuration Protocol (DHCP) server service for the specific failover relationship name.
If the *Name* parameter is not specified, this cmdlet returns all failover relationships defined on the DHCP server service.
If the *Name* parameter does not match a failover relationship, a non-terminating error will be returned for the specific *Name* parameter value.

If the *ScopeId* parameter is specified, the failover relationships of which the specified scopes are included are returned.
The *ScopeId* parameter values should be failover scopes.

## EXAMPLES

### Example 1: Get failover information for a relationship
```
PS C:\> Get-DhcpServerv4Failover -ComputerName "dhcpserver.contoso.com" -Name "SFO-SIN-Failover"
```

This example gets the failover relationship information for relationship named SFO-SIN-Failover on the DHCP server service that runs on the computer named dhcpserver.contoso.com.

### Example 2: Get failover information for all relationships
```
PS C:\> Get-DhcpServerv4Failover -ComputerName "dhcpserver.contoso.com"
```

This example gets the failover relationship information for all of the failover relationships on the DHCP server service that runs on the computer named dhcpserver.contoso.com.

### Example 3: Get failover information for a relationship that contains a scope
```
PS C:\> Get-DhcpServerv4Failover -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0
```

This example gets the failover relationship information for the failover relationship of which the scope 10.10.10.0 is a part, on the DHCP server service that runs on the computer named dhcpserver.contoso.com.

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

### -Name
Specifies one or more names of failover relationships for which the properties are returned.

```yaml
Type: String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScopeId
Specifies one or more scope identifiers (IDs), in IPv4 address format.
The properties of the failover relationships on the DHCP server service to which these scopes are associated are returned.

```yaml
Type: IPAddress[]
Parameter Sets: ScopeId
Aliases:

Required: True
Position: Named
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Failover[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4Failover](./Add-DhcpServerv4Failover.md)

[Add-DhcpServerv4FailoverScope](./Add-DhcpServerv4FailoverScope.md)

[Invoke-DhcpServerv4FailoverReplication](./Invoke-DhcpServerv4FailoverReplication.md)

[Remove-DhcpServerv4Failover](./Remove-DhcpServerv4Failover.md)

[Remove-DhcpServerv4FailoverScope](./Remove-DhcpServerv4FailoverScope.md)

[Set-DhcpServerv4Failover](./Set-DhcpServerv4Failover.md)

