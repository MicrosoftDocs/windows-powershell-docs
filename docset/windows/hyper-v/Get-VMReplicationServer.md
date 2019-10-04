---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-VMReplicationServer
ms.reviewer:
ms.assetid: 93652B26-419B-4FC6-81C6-0AC9C35460EF
---

# Get-VMReplicationServer

## SYNOPSIS
Gets the replication and authentication settings of a Replica server.

## SYNTAX

### ComputerName (Default)
```
Get-VMReplicationServer [[-ComputerName] <String[]>] [[-Credential] <PSCredential[]>] [<CommonParameters>]
```

### CimSession
```
Get-VMReplicationServer [-CimSession] <CimSession[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMReplicationServer** cmdlet gets the replication and authentication settings of a Replica server.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMReplicationServer
```

This example gets the replication configuration of the local Replica server.

### Example 2
```
PS C:\> Get-VMReplicationServer server01.domain01.contoso.com
```

This example gets the replication configuration of a server named server01.domain01.contoso.com.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: CimSession
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-v hosts which run this cmdlet.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: ComputerName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: ComputerName
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMReplicationServer

## NOTES

## RELATED LINKS

