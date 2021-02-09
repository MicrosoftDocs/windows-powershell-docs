---
external help file: MSFT_NCSIPolicyConfiguration.cdxml-help.xml
Module Name: NetworkConnectivityStatus
online version: 
schema: 2.0.0
title: Get-NCSIPolicyConfiguration
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: AD6DD8E8-6C58-456B-8C05-43F59567141F
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-NCSIPolicyConfiguration

## SYNOPSIS
Gets the Network Connectivity Status indicator configuration on a specified store, either the active store on the local connection or on a Group Policy object.

## SYNTAX

```
Get-NCSIPolicyConfiguration [-PolicyStore <String>] [-GPOSession <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
This **Get-NCSIPolicyConfiguration** cmdlet gets the Network Connectivity Status indicator configuration on a specified store, either the active store on the local connection or on a Group Policy object.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-NCSIPolicyConfiguration -PolicyStore "contoso\johnj99"
Description                    : NCSI Configuration 
CorporateDNSProbeHostAddress   : 2001:4898:1337:1337:1337::1337 
CorporateDNSProbeHostName      : corp.contoso.com 
CorporateSitePrefixList        : 2001:4898::/32,2006:1601::/32,2a01:0110::/31 
CorporateWebsiteProbeURL       : http://web.contoso.com 
DomainLocationDeterminationURL : https://io.contoso.com
```

This example returns the NCSI configuration of the specified GPO.

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

### -GPOSession
Specifies the Group Policy session for which the cmdlet should pull configuration information from.
This parameter can be used in conjunction with the NetGPO cmdlet family to aggregate multiple operations that are performed on a Group Policy Object. 
                         
This parameter cannot be used in conjunction with the **PolicyStore** parameter. 
                         
Using this parameter aggregates multiple cmdlets to run against a local GPO cache. 
                         
This is a common parameter across networking with very little difference between them.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyStore
Specifies the policy store for which the cmdlet should pull configuration information from.
This cmdlet supports getting information from a Group Policy Object, in the form `Domain\GPOName`.
It also supports getting the active configuration on a local computer, using ActiveStore. 
                         
This is a common parameter across networking with very little difference between them.

```yaml
Type: String
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/StandardCimv2/MSFT_NCSIPolicyConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DAConnectionStatus](./Get-DAConnectionStatus.md)

[Reset-NCSIPolicyConfiguration](./Reset-NCSIPolicyConfiguration.md)

[Set-NCSIPolicyConfiguration](./Set-NCSIPolicyConfiguration.md)

