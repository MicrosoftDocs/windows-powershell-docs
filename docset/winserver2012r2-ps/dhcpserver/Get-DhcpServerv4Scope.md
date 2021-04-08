---
author: Kateyanne
description: 
external help file: PS_DhcpServerV4Scope_v1.0.0.cdxml-help.xml
manager: jasgro
Module Name: DhcpServer
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv4scope?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DhcpServerv4Scope
---

# Get-DhcpServerv4Scope

## SYNOPSIS
Returns the IPv4 scope configuration of the specified scopes.

## SYNTAX

```
Get-DhcpServerv4Scope [-ComputerName <String>] [[-ScopeId] <IPAddress[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DhcpServerv4Scope** cmdlet returns the IPv4 scope configuration of the specified scopes.
If the **ScopeId** parameter is not specified, then all of the scopes configured on the Dynamic Host Configuration Protocol (DHCP) server service are returned.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DhcpServerv4Scope -ComputerName dhcpserver.contoso.com
```

This example gets all of the scopes present on the DHCP server service running on the computer named dhcpserver.contoso.com.

### EXAMPLE 2
```
PS C:\>Get-DhcpServerv4Scope -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0
```

This example gets the specified scope present on the DHCP server service running on the computer named dhcpserver.contoso.com.

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
Aliases: Session

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
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScopeId
Specifies one or more scope identifiers (IDs), in IPv4 address format, from which the configuration is to be retrieved.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4Scope](./Add-DhcpServerv4Scope.md)

[Get-DhcpServerv4ScopeStatistics](./Get-DhcpServerv4ScopeStatistics.md)

[Remove-DhcpServerv4Scope](./Remove-DhcpServerv4Scope.md)

[Set-DhcpServerv4Scope](./Set-DhcpServerv4Scope.md)

