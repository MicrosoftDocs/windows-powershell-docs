---
external help file: Microsoft.Protocols.Tools.PowerShell.dll-Help.xml
Module Name: PEF
online version: 
schema: 2.0.0
title: Add-PefProviderConfig
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: B8AB15F8-55CD-4909-B312-1A94AAB2F45A
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Add-PefProviderConfig

## SYNOPSIS
Adds a provider to a remote Trace Session on a target host.

## SYNTAX

```
Add-PefProviderConfig [-TargetHost <PefTargetHost>] [-Provider <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-PefProviderConfig** cmdlet adds a provider to the remote session configured by using a friendly name.
Do not specify a GUID.

You access provider configuration by using the object that this cmdlet creates.
You can configure provider error levels, event keywords, and other provider-specific options for providers such as the Microsoft-Windows-NDIS-PacketCapture, Microsoft-Pef-WebProxy, and Microsoft-Pef-WPF.
Use this object as input for the Add-PefMessageSource cmdlet.

## EXAMPLES

### Example 1: Create and configure a remote trace to a named server
```
PS C:\> $targetHost = New-PefTargetHost -ComputerName "Server07"
PS C:\> $th1p1Config = $targetHost | Add-PefProviderConfig -Provider "Microsoft-Windows-NDIS-PacketCapture"
PS C:\> $th1p1Config.Configurations[0].TruncationLength = 128
PS C:\> $th1p1Config.Configurations[0].Interfaces[0].Enabled=0
PS C:\> $th1p1Config.Configurations[0].Interfaces[3].Enabled=1
PS C:\> $TraceSession01 = New-PefTraceSession -Force -Path "C:\Trace01" -SaveOnStop | Add-PefMessageSource -Source $targetHost | Start-PefTraceSession
```

The first command creates a target host for the computer named Server07, by using the New-PefTargetHost cmdlet, and then stores that host in the **$targetHost** variable.

The second command passes the host stored in **$targetHost** to the current cmdlet, by using the pipeline operator.
This cmdlet adds a provider, and then stores the result in the **$th1p1Config** variable.

The third, fourth, and fifth commands use standard dot notation to refer to elements of the configuration stored in **$th1p1Config**, and assign values to those elements.
These commands set the truncation level to 128,  disables all interfaces, and then re-enables node 3.
The re-enabled node might contain multiple child nodes.
These nodes are enabled subsequently.

The final command creates a session, adds the target host as the session source, and starts the trace session, by using the New-PefTraceSession, Add-PefMessageSource, and Start-PefTraceSession cmdlets.
The final command stores the new session in the **$TraceSession01** variable.
This session encapsulates the configuration settings of  up in the previous commands in this example.

## PARAMETERS

### -Provider
Specifies the friendly name for a message provider.

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

### -TargetHost
Specifies a target host object that represents a remote computer that you configure for a remote Live Trace Session.
To obtain a target host object, use the New-PefTargetHost cmdlet.

```yaml
Type: PefTargetHost
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-PefTargetHost](./New-PefTargetHost.md)

[New-PefTraceSession](./New-PefTraceSession.md)

[Add-PefMessageSource](./Add-PefMessageSource.md)

[Start-PefTraceSession](./Start-PefTraceSession.md)

