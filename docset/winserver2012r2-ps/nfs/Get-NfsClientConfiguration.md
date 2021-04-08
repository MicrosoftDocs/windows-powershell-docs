---
author: Kateyanne
description: 
external help file: MSFT_NfsClientConfig.cmdletDefinition.cdxml-help.xml
manager: jasgro
Module Name: NFS
ms.author: v-kaunu
ms.date: 10/29/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/nfs/get-nfsclientconfiguration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NfsClientConfiguration
---

# Get-NfsClientConfiguration

## SYNOPSIS
Gets configuration settings for an NFS client.

## SYNTAX

```
Get-NfsClientConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NfsClientConfiguration** cmdlet gets a configuration object for a Network File System (NFS) client.
You can use the **Set-NfsClientConfiguration** cmdlet to change NFS client settings.

## EXAMPLES

### Example 1: Get NFS client configuration settings
```
PS C:\> Get-NfsClientConfiguration
Service State          : Running
Case-sensitive Lookups : Disabled
Default Access Mode    : 755
Mount Type             : SOFT
Mount Retry Attempts   : 1
RPC Timeout (seconds)  : 8
Read Buffer Size (KB)  : 1024
Write Buffer Size (KB) : 1024
Use Reserved Ports     : Enabled
Authentication         : {sys, Krb5, Krb5i, Krb5p}
Transport Protocol     : {TCP, UDP}
```

This command gets NFS client configuration settings on a local computer.

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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsClientConfig

## NOTES

## RELATED LINKS

[Set-NfsClientConfiguration](./Set-NfsClientConfiguration.md)

