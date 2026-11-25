---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerV4ExclusionRange_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv4exclusionrange?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DhcpServerv4ExclusionRange
---

# Get-DhcpServerv4ExclusionRange

## SYNOPSIS
Returns the IPv4 address ranges excluded from the specified scope IDs.

## SYNTAX

```
Get-DhcpServerv4ExclusionRange [-ComputerName <String>] [[-ScopeId] <IPAddress[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DhcpServerv4ExclusionRange** cmdlet returns the IPv4 address ranges excluded from the specified scope identifiers (IDs).
If the *ScopeId* parameter is not specified, all IPv4 address ranges excluded on the Dynamic Host Configuration Protocol (DHCP) server service are returned.

## EXAMPLES

### Example 1: Get all address ranges excluded from all scopes on the DHCP server service
```
PS C:\> Get-DhcpServerv4ExclusionRange -ComputerName "dhcpserver.contoso.com"
```

This example gets all the excluded IPv4 address ranges on the specified DHCP server service that runs on the computer named dhcpserver.contoso.com.

### Example 2: Get all address ranges excluded from a scope on the DHCP server service
```
PS C:\> Get-DhcpServerv4ExclusionRange -ComputerName "dhcpserver.contoso.com" -ScopeId 10.10.10.0
```

This example gets all the excluded IPv4 address ranges in the specified scope on the specified DHCP server service that runs on the computer named dhcpserver.contoso.com.

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

### -ScopeId
Specifies the scope IDs, in IPv4 address format, from which the excluded IP address ranges are returned.

```yaml
Type: IPAddress[]
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4ExclusionRange[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4ExclusionRange](./Add-DhcpServerv4ExclusionRange.md)

[Remove-DhcpServerv4ExclusionRange](./Remove-DhcpServerv4ExclusionRange.md)

