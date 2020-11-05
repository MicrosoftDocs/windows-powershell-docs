---
external help file: MSFT_NfsMountedClient.cmdletDefinition.cdxml-help.xml
Module Name: NFS
online version: 
schema: 2.0.0
title: Get-NfsMountedClient
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: E1F71CF4-D149-4CA2-B8A6-BFF510B546D1
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-NfsMountedClient

## SYNOPSIS
Gets clients that are connected to an NFS server.

## SYNTAX

```
Get-NfsMountedClient [[-ClientId] <UInt64[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-NfsMountedClient** cmdlet gets clients that are connected to a Network File System (NFS) server using the NFS v4.1 protocol.

## EXAMPLES

### Example 1: Get all mounted clients from a local NFS server
```
PS C:\> Get-NfsMountedClient
```

This command gets all the mounted clients from a local NFS server.

### Example 2: Get a specified mounted client from a local NFS server
```
PS C:\> Get-NfsMountedClient -ClientId 101
```

This command gets a mounted client that has the client identifier 101 from a local NFS server.

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

### -ClientId
Specifies the ID of a client that is connected to an NFS server.
By default, the cmdlet gets all mounted clients.

```yaml
Type: UInt64[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/NFS/MSFT_NfsMountedClient

## NOTES

## RELATED LINKS

[Revoke-NfsMountedClient](./Revoke-NfsMountedClient.md)

