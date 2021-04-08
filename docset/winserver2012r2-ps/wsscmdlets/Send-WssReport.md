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
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/send-wssreport?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Send-WssReport
---

# Send-WssReport

## SYNOPSIS
Sends out a health report instance.

## SYNTAX

```
Send-WssReport [-Id] <Guid> [<CommonParameters>]
```

## DESCRIPTION
The **Send-WssReport** cmdlet sends out a health report instance through email by using the ID of the report.

## EXAMPLES

### Example 1: Send a health report
```
PS C:\> $Reports = Get-WssReport
PS C:\> Send-WssReport $Reports[0].Id
```

The first command uses the Get-WssReport cmdlet to get all instances of reports, and saves the results in the $Reports variable.

The second command sends an instance of a health report by using the ID of the first instance in the $Reports variable.

### 1:
```
PS C:\>
```

## PARAMETERS

### -Id
Specifies the GUID of a health report instance.

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
Report Guid

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssReport](./Get-WssReport.md)

[New-WssReport](./New-WssReport.md)

[Remove-WssReport](./Remove-WssReport.md)

