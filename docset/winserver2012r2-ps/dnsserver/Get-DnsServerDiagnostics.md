---
external help file: PS_DnsServerDiagnostics_v1.0.0.cdxml-help.xml
Module Name: DnsServer
online version: 
schema: 2.0.0
title: Get-DnsServerDiagnostics
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 6DA4139A-9D29-4913-8658-8640EE0F22B7
---

# Get-DnsServerDiagnostics

## SYNOPSIS
Retrieves DNS event logging details.

## SYNTAX

```
Get-DnsServerDiagnostics [-ComputerName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsServerDiagnostics** cmdlet retrieves Domain Name System (DNS) server diagnostic and logging parameters.

## EXAMPLES

### Example 1: Get DNS event logging details
```
PS C:\> Get-DnsServerDiagnostics
SaveLogsToPersistentStorage          : False

Queries                              : False

Answers                              : False

Notifications                        : False

Update                               : False

QuestionTransactions                 : False

UnmatchedResponse                    : False

SendPackets                          : False

ReceivePackets                       : False

TcpPackets                           : False

UdpPackets                           : False

FullPackets                          : False

FilterIPAddressList                  :

EventLogLevel                        : 4

UseSystemEventLog                    : False

EnableLoggingToFile                  : True

EnableLogFileRollover                : False

LogFilePath                          :

MaxMBFileSize                        : 500000000

WriteThrough                         : False

EnableLoggingForLocalLookupEvent     : False

EnableLoggingForPluginDllEvent       : False

EnableLoggingForRecursiveLookupEvent : False

EnableLoggingForRemoteServerEvent    : False

EnableLoggingForServerStartStopEvent : False

EnableLoggingForTombstoneEvent       : False

EnableLoggingForZoneDataWriteEvent   : False

EnableLoggingForZoneLoadingEvent     : False
```

This command gets DNS event logging details for the local DNS server.

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
Specifies a DNS server.
The acceptable values for this parameter are: an IP V4 address; an IP V6 address; any other value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerDiagnostics

## NOTES

## RELATED LINKS

[Set-DnsServerDiagnostics](./Set-DnsServerDiagnostics.md)

