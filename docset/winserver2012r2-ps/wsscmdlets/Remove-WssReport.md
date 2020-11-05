---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Remove-WssReport
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: A3A38C3A-5310-48FB-BD69-2CF18AE1F587
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-WssReport

## SYNOPSIS
Removes a health report instance.

## SYNTAX

```
Remove-WssReport [-Id] <Guid> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WssReport** cmdlet removes a single health report instance identified by its ID.

## EXAMPLES

### Example 1: Remove an instance of a health report
```
PS C:\> $Reports = Get-WssReport
PS C:\> Remove-WssReport $Reports[0].Id
```

The first command uses the Get-WssReport cmdlet to get all instances of reports, and saves the results in the $Reports variable.

The second command removes an instance of a health report by using the ID of the first instance in the $Reports variable.

### 1:
```
PS C:\>
```

## PARAMETERS

### -Id
Specifies the ID of a health report instance.
The cmdlet removes the health report instance that you specify.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Guid
Report

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssReport](./Get-WssReport.md)

[New-WssReport](./New-WssReport.md)

[Send-WssReport](./Send-WssReport.md)

