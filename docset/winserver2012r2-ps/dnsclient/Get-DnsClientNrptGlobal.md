---
external help file: PS_DnsClientNRPTGlobal_v1.0.0.cdxml-help.xml
Module Name: DnsClient
online version: 
schema: 2.0.0
title: Get-DnsClientNrptGlobal
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: AE7B2DEE-7132-4CCA-90D0-8BA1A1D885AB
---

# Get-DnsClientNrptGlobal

## SYNOPSIS
Retrieves the Name Resolution Policy Table (NRPT) global settings.

## SYNTAX

```
Get-DnsClientNrptGlobal [-Server <String>] [-GpoName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsClientNrptGlobal** cmdlet retrieves the following Name Resolution Policy Table (NRPT) details: 

 -- DirectAccess (DA) settings. 

 -- DNS client query policy. 

 -- DNS client name resolution fallback policy.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DnsClientNrptGlobal
EnableDAForAllNetworks                  QueryPolicy                             SecureNameQueryFallback                
----------------------                  -----------                             -----------------------                
Disable                                 Disable                                 Disable
```

This example retrieves the global NRPT settings.

### EXAMPLE 2
```
PS C:\>Get-DnsClientNrptGlobal -GpoName "corp.contoso.com\DirectAccess Client Settings"
```

This example retrieves the global NRPT settings for the GPO named DirectAccess Client Settings that is linked to corp.contoso.com.

### EXAMPLE 3
```
PS C:\>Get-DnsClientNrptGlobal -GpoName "corp.contoso.com\DirectAccess Client Settings" -Server dc1
```

This example retrieves the global NRPT settings for the GPO named DirectAccess Client Settings that is linked to corp.contoso.com on the server named dc1.

### EXAMPLE 4
```
PS C:\>Get-DnsClientNrptGlobal -GpoName "corp.contoso.com\DirectAccess Client Settings" -CimSession 2-dc1.corp2.corp.contoso.com
```

This example retrieves the global NRPT settings for the GPO named DirectAccess Client Settings that is linked to corp.contoso.com on the remote computer named 2-dc1.corp2.corp.contoso.com.

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

### -GpoName
Specifies the name of Group Policy Object (GPO).
If this parameter is not specified, then the default NRPT settings are retrieved.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Server
Specifies the server hosting the GPO.
This parameter is only applicable with the **GpoName** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DNS/DnsClientNrptGlobal
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DnsClientNrptGlobal object contains all of the properties of the DNS client NRPT global settings.

## NOTES

## RELATED LINKS

[Add-DnsClientNrptRule](./Add-DnsClientNrptRule.md)

[Get-DnsClientNrptPolicy](./Get-DnsClientNrptPolicy.md)

[Get-DnsClientNrptRule](./Get-DnsClientNrptRule.md)

[Remove-DnsClientNrptRule](./Remove-DnsClientNrptRule.md)

[Set-DnsClientNrptGlobal](./Set-DnsClientNrptGlobal.md)

[Set-DnsClientNrptRule](./Set-DnsClientNrptRule.md)

