---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssClientBackup
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: A1356554-499C-45F6-9DE6-479D8ACA716D
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssClientBackup

## SYNOPSIS
Gets information about client backup jobs.

## SYNTAX

### ByName (Default)
```
Get-WssClientBackup [-ComputerName] <String> [<CommonParameters>]
```

### BySid
```
Get-WssClientBackup [-ComputerSid] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssClientBackup** cmdlet gets information about client backup jobs for a computer.
Specify a computer by name or security identifier (SID).

## EXAMPLES

### Example 1: Get client backup job information
```
PS C:\> Get-WssClientBackup -ComputerName "Workstation073"
```

This command gets information for client backup jobs for a computer named Workstation073.

## PARAMETERS

### -ComputerName
Specifies the name of a computer.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerSid
Specifies the SID of a computer.

```yaml
Type: String
Parameter Sets: BySid
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.PCBackup.BackupUtil.WcfContracts.ClientJobInfo
This cmdlet returns client job information.

## NOTES

## RELATED LINKS

[Disable-WssClientBackup](./Disable-WssClientBackup.md)

[Enable-WssClientBackup](./Enable-WssClientBackup.md)

[Set-WssClientBackup](./Set-WssClientBackup.md)

[Start-WssClientBackup](./Start-WssClientBackup.md)

[Stop-WssClientBackup](./Stop-WssClientBackup.md)

