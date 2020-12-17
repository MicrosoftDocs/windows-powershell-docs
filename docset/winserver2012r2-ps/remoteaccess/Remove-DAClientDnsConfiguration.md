---
external help file: PS_DAClientDNSConfiguration_v1.0.0.cdxml-help.xml
online version: 
schema: 2.0.0
title: Remove-DAClientDnsConfiguration
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 198BE1E9-4CB6-464D-9A5A-8A5F9E9A9127
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-DAClientDnsConfiguration

## SYNOPSIS
Removes the Name Resolution Policy Table (NRPT) entry corresponding to the specified DNS suffix from the NRPT.

## SYNTAX

```
Remove-DAClientDnsConfiguration [-DnsSuffix] <String[]> [-ComputerName <String>] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DAClientDnsConfiguration** cmdlet removes the Name Resolution Policy Table (NRPT) entry corresponding to the specified DNS suffix from the NRPT.

In a multi-domain scenario; when an NRPT entry is removed, the entry is correspondingly deleted from the all the client GPOs in various domains.
Note: In a Windows deployment with firstref_server_7 GPOs, removal of a suffix will removes it from both the Windows Server 2008 R2 GPOs and Windows Server® 2012 GPOs

The NRPT configuration is applicable globally to the entire DA deployment and therefore is not impacted by multi-site deployments.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Remove-DAClientDnsConfiguration -DnsSuffix 'contoso.com' -PassThru
Name                             : 
Version                          : 1 
Namespace                        : {hrnet.com} 
IPsecCARestriction               : 
DirectAccessDnsServers           : fdad:34fb:a649:7777::404:404 
DirectAccessEnabled              : True 
DirectAccessProxyType            : Direct 
DirectAccessProxyName            : 
DirectAccessQueryIPsecEncryption : None 
DirectAccessQueryIPsecRequired   : False 
NameServers                      : 
DnsSecEnabled                    : 
DnsSecQueryIPsecEncryption       : None 
DnsSecQueryIPsecRequired         : False 
DnsSecValidationRequired         : False 
NameEncoding                     : 
DisplayName                      : 
Comment                          :
```

This example removes the NRPT rules for contoso.com from DA configuration.
This change is propagated across all of the client GPOs.

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
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the Remote Access server computer specific tasks should be run.

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

### -DnsSuffix
Specifies a list of DNS suffixes.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Namespace

Required: True
Position: 1
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsClientNRPTRule[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The array of DnsClientNRPTRule objects contains the following properties: 

 -- The NRPT object for the NRPT entry that was removed.

## NOTES

## RELATED LINKS

[Add-DAClientDnsConfiguration](./Add-DAClientDnsConfiguration.md)

[Get-DAClientDnsConfiguration](./Get-DAClientDnsConfiguration.md)

[Set-DAClientDnsConfiguration](./Set-DAClientDnsConfiguration.md)

