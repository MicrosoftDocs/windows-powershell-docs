---
ms.technology: 
ms.mktglfcycl: manage
ms.author: v-kaunu
ms.prod: w10
ms.sitesec: library
author: Kateyanne
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: AppVServerCmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: EC75B56F-E5EA-4598-BE54-FE0BE8E57068
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Import-AppvServerPackage
---

# Import-AppvServerPackage

## SYNOPSIS
Adds a package to the App-V Management server.

## SYNTAX

```
Import-AppvServerPackage [-PackagePath] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-AppvServerPackage** cmdlet accepts a path to a valid APPV package.
The specified package is imported into the Microsoft Application Virtualization (App-V) Management server and an object to the package is returned.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -PackagePath
Specifies full path to the App-V package.
This can either be an SMB or HTTP/HTTPS path.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### AppvServer.AppvServerPackage

## NOTES

## RELATED LINKS

[Get-AppvServerPackage](./Get-AppvServerPackage.md)

[Grant-AppvServerPackage](./Grant-AppvServerPackage.md)

[Publish-AppvServerPackage](./Publish-AppvServerPackage.md)

[Remove-AppvServerPackage](./Remove-AppvServerPackage.md)

[Set-AppvServerPackage](./Set-AppvServerPackage.md)

[Unpublish-AppvServerPackage](./Unpublish-AppvServerPackage.md)


