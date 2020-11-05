---
external help file: PS_RemoteAccessRoutingDomain_v1.0.cdxml-help.xml
online version: 
schema: 2.0.0
title: Enable-RemoteAccessRoutingDomain
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 45A60B09-63C0-4170-8DB2-11A2B6024F69
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Enable-RemoteAccessRoutingDomain

## SYNOPSIS
Enables VPN or S2S functions for a specified routing domain.

## SYNTAX

```
Enable-RemoteAccessRoutingDomain [-Name] <String> [-PassThru] -Type <EnableType> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-RemoteAccessRoutingDomain** cmdlet enables virtual private network (VPN), site to site (VPNS2S) or all functions for a tenant on a multitenant gateway.

## EXAMPLES

### Example 1: Enables routing in a domain
```
PS C:\> Enable-RemoteAccessRoutingDomain  -Name  Rd_01 -Type All
```

This command enables all functions for the routing domain named Rd_01.

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

### -Name
Specifies the name of a routing domain.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RoutingDomainName, RoutingDomain

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### -Type
Specifies the type of remote access.
The acceptable values for this parameter are:

- Vpn
- VpnS2S
- All

```yaml
Type: EnableType
Parameter Sets: (All)
Aliases: 
Accepted values: Vpn, VpnS2S, All

Required: True
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#RoutingDomainConfiguration

## NOTES

## RELATED LINKS

[Disable-RemoteAccessRoutingDomain](./Disable-RemoteAccessRoutingDomain.md)

[Get-RemoteAccessRoutingDomain](./Get-RemoteAccessRoutingDomain.md)

[Set-RemoteAccessRoutingDomain](./Set-RemoteAccessRoutingDomain.md)

