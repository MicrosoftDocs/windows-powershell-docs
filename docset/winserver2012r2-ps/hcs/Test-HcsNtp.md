---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Test-HcsNtp
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: DA2E5D7F-EA06-4CEE-935E-A5B56DBE4670
---

# Test-HcsNtp

## SYNOPSIS
Attempts to synchronize the time to the NTP server.

## SYNTAX

```
Test-HcsNtp [-NtpServer <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-HcsNtp** cmdlet attempts to synchronize the time to the Network Time Protocol (NTP) server for the device, and reports the results.

## EXAMPLES

### Example 1: Test NTP configuration
```
PS C:\> Test-HcsNtp
LeapIndicator          : 0(no warning)
Stratum                : 3 (secondary reference - syncd by (S)NTP)
Precision              : -6 (15.625ms per tick)
RootDelay              : 0.1249761s
RootDisperion          : 7.8620298s
ReferenceId            : 0x0BDA0145 (source IP:  10.118.1.85)
LastSuccessfulSyncTime : 1/30/2014 9:53:03 AM
Source                 : time.contoso.com
PollInterval           : 13 (8192s)
```

This command tests whether the NTP configuration for the device is valid.

## PARAMETERS

### -NtpServer
{{Fill NtpServer Description}}

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-HcsNtpClientServerAddress](./Get-HcsNtpClientServerAddress.md)

[Set-HcsNtpClientServerAddress](./Set-HcsNtpClientServerAddress.md)

