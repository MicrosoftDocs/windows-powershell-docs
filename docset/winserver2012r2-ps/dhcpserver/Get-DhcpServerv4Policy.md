---
external help file: PS_DhcpServerv4Policy_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
online version: 
schema: 2.0.0
title: Get-DhcpServerv4Policy
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: FDB720CC-4DC2-45E2-AB48-A04F069FCF76
---

# Get-DhcpServerv4Policy

## SYNOPSIS
Gets one or more policies at the server level or the scope level.

## SYNTAX

```
Get-DhcpServerv4Policy [-ComputerName <String>] [[-Name] <String[]>] [[-ScopeId] <IPAddress>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DhcpServerv4Policy** cmdlet gets one or more policies at the server level or the scope level.

If the **Name** and **ScopeId** parameters are specified, then the policy from the specified scope is retrieved.

If only the **ScopeId** parameter is specified, then all of the policies in the specified scope are retrieved.

If only the **Name** parameter is specified, then that specific server level policy is retrieved.

If neither the **Name** nor the **ScopeId** parameter is specified, then all of the server level policies are retrieved.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DhcpServerv4Policy -ComputerName dhcpserver.contoso.com -Name PrinterPolicy
```

This example gets the policy properties for the policy named PrinterPolicy that is defined as a server level, or server-wide, policy.

### EXAMPLE 2
```
PS C:\>Get-DhcpServerv4Policy -ComputerName dhcpserver.contoso.com -Name HyperVPolicy -ScopeId 10.10.10.0
```

This example gets the policy properties for the policy named HyperVPolicy that is defined inside the scope 10.10.10.0.

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
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the Dynamic Host Configuration Protocol (DHCP) server service.

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
Specifies one or more names of the policies to be returned.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScopeId
Specifies the scope identifier, in IPv4 address format, from which the policies are to be retrieved. 
                         
If this parameter is not specified, then the server level policies are retrieved.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Policy
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Policy[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4Policy](./Add-DhcpServerv4Policy.md)

[Add-DhcpServerv4PolicyIPRange](./Add-DhcpServerv4PolicyIPRange.md)

[Get-DhcpServerv4PolicyIPRange](./Get-DhcpServerv4PolicyIPRange.md)

[Remove-DhcpServerv4Policy](./Remove-DhcpServerv4Policy.md)

[Remove-DhcpServerv4PolicyIPRange](./Remove-DhcpServerv4PolicyIPRange.md)

[Set-DhcpServerv4Policy](./Set-DhcpServerv4Policy.md)

