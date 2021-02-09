---
external help file: MSFT_WdsMulticastClient_v1.0.cdxml-help.xml
Module Name: WDS
online version: 
schema: 2.0.0
title: Disconnect-WdsMulticastClient
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 6844AAD1-7C35-4C4F-9D55-FE60358CBFF0
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Disconnect-WdsMulticastClient

## SYNOPSIS
Disconnects a multicast client from a transmission or namespace.

## SYNTAX

```
Disconnect-WdsMulticastClient -Id <UInt32> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Disconnect-WdsMulticastClient** cmdlet disconnects a multicast client from a transmission or namespace.
To obtain an ID for a multicast client, use the **Get-WdsMulticastClient** cmdlet.
You can allow the client to restart deployment using a unicast transmission, or just disconnect the client from the Windows Deployment Services server.

## EXAMPLES

### Example 1: Disconnect a client
```
PS C:\> Disconnect-WdsMulticastClient -Id 34 -Force
```

This command disconnects a Windows Deployment Services multicast client identified by the ID 34.

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

### -Force
Indicates that the cmdlet disconnects any clients currently connected to the multicast transmission.
If you do not specify this parameter, the client will be able to restart the transmission and download the content using a unicast transmission.

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

### -Id
Specifies an ID.
This is the ID of a multicast client to disconnect.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

## NOTES

## RELATED LINKS

[Get-WdsMulticastClient](./Get-WdsMulticastClient.md)

