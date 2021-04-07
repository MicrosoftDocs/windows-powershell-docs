---
author: Kateyanne
description: 
external help file: WssCmdlets.dll-Help.xml
manager: jasgro
Module Name: WSSCmdlets
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssaddin?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssAddIn
---

# Get-WssAddIn

## SYNOPSIS
Gets installed add-ins.

## SYNTAX

```
Get-WssAddIn [[-Id] <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssAddIn** cmdlet gets the add-ins for an installed package.
If you do not specify the **Id** parameter, the cmdlet gets all installed add-ins on the local computer.

## EXAMPLES

### Example 1: Get all installed add-ins
```
PS C:\> Get-WssAddIn
```

This command gets all add-ins installed on the local computer.

## PARAMETERS

### -Id
Specifies the GUID for an installed package.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.AddinInfrastructure.PackageInfo
This cmdlet returns package information of specific add-ins.

## NOTES

## RELATED LINKS

[Install-WssAddIn](./Install-WssAddIn.md)

[Uninstall-WssAddIn](./Uninstall-WssAddIn.md)

