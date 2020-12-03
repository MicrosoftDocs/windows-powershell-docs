---
ms.technology: 
ms.mktglfcycl: manage
ms.author: v-kaunu
ms.prod: w10
ms.sitesec: library
author: Kateyanne
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: A1E27CB0-DA01-46BF-8542-6EE7B2FDFB77
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Disable-MbamReport
ms.reviewer:
---

# Disable-MbamReport

## SYNOPSIS
Disables the Reports feature.

## SYNTAX

```
Disable-MbamReport [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-MbamReport** cmdlet disables the Microsoft BitLocker Administration and Monitoring (MBAM) Reports feature.

## EXAMPLES

### Example 1: Disable the Reports feature
```
PS C:\> Disable-MbamReport
Are you sure you want to perform this action?
Performing operation "Disable MBAM Reports feature"
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

This command disables the Reports feature.
The command does not specify the *Force* parameter, and, therefore, the command prompts you for confirmation.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Indicates that the cmdlet performs the operation without prompting you for confirmation.

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

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-MbamReport](enable-mbamreport.md)

[Get-MbamReport](get-mbamreport.md)

[Test-MbamReport](test-mbamreport.md)


