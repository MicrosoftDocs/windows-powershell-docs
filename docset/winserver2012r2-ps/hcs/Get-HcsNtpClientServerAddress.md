---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-HcsNtpClientServerAddress
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 1EBBE656-910C-47DB-8BA4-A80603C9D094
---

# Get-HcsNtpClientServerAddress

## SYNOPSIS
Gets URLs of the NTP servers for this device.

## SYNTAX

```
Get-HcsNtpClientServerAddress [<CommonParameters>]
```

## DESCRIPTION
The **Get-HcsNtpClientServerAddress** cmdlet gets the URLs of the Network Time Protocol (NTP) servers for this device.

## EXAMPLES

### Example 1: Get NTP server addresses
```
PS C:\> Get-HcsNtpClientServerAddress
Primary                                                     Secondary
-------                                                     ---------
time.contoso.com                                            {secondary.contoso.com}
```

This command gets addresses of NTP client servers.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HCS.Management.Powershell.Cmdlets.NtpInfo
This cmdlet returns an **NtpInfo** object that has the following properties:

- Primary NTP Address.
This is a single string. 
- Secondary NTP Addresses.
This is an array of strings.

The NtpInfo object has the following properties:

- String Primary 
- String\[\] Secondary

## NOTES

## RELATED LINKS

[Set-HcsNtpClientServerAddress](./Set-HcsNtpClientServerAddress.md)

