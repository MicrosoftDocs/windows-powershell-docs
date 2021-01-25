---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Get-VM
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 2CCE78AD-E5BD-4A56-944C-2832323ACF26
---

# Get-VM

## SYNOPSIS
Gets the virtual machines from one or more Hyper-V hosts.

## SYNTAX

### Name (Default)
```
Get-VM [-ComputerName <String[]>] [[-Name] <String[]>] [<CommonParameters>]
```

### Id
```
Get-VM [-ComputerName <String[]>] [[-Id] <Guid>] [<CommonParameters>]
```

### ClusterObject
```
Get-VM [-ClusterObject] <PSObject> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VM** cmdlet gets the virtual machines from one or more Hyper-V hosts.

## EXAMPLES

### Example 1
```
PS C:\>Get-VM
```

This example gets all virtual machines on the local virtual machine host.

### Example 2
```
PS C:\>Get-VM -ComputerName Server1 | Where-Object {$_.State -eq 'Running'}
```

This example gets all virtual machines on Hyper-V host Server1 that are running.

### Example 3
```
PS C:\>Get-ClusterGroup | ? {$_.GroupType -eq 'VirtualMachine' } | Get-VM
```

This example gets all virtual machines in the cluster to which the local Hyper-V host is joined.

## PARAMETERS

### -ClusterObject
Specifies the cluster resource or cluster group of the virtual machine to be retrieved.

```yaml
Type: PSObject
Parameter Sets: ClusterObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts from which virtual machines are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: Name, Id
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the identifier of the virtual machine to be retrieved.

```yaml
Type: Guid
Parameter Sets: Id
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual machine to be retrieved.

```yaml
Type: String[]
Parameter Sets: Name
Aliases: VMName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VirtualMachine

## NOTES

## RELATED LINKS

