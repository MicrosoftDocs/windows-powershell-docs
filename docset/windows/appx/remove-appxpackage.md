---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: Appx
ms.assetid: 00607943-4ED6-4BFB-B2AF-B43BD542722C
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer:
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/appx/remove-appxpackage
schema: 2.0.0
title: Remove-AppxPackage
---

# Remove-AppxPackage

## SYNOPSIS
Removes an app package from one or more user accounts.

## SYNTAX

```
Remove-AppxPackage [-Package] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

```
Remove-AppxPackage [-Package] <String> [-AllUsers] [-Confirm] [-WhatIf] [<CommonParameters>]
```

```
Remove-AppxPackage [-Package] <String> [-PreserveApplicationData] [-Confirm] [-WhatIf] [<CommonParameters>]
```

```
Remove-AppxPackage [-Package] <String> -User <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
## DESCRIPTION
The **Remove-AppxPackage** cmdlet removes an app package from a user account.
An app package has an .appx file name extension.

## EXAMPLES

### Example 1: Remove an app package
```
PS C:\>Remove-AppxPackage -Package "package1_1.0.0.0_neutral__8wekyb3d8bbwe"
```

This command removes an app package named package1_1.0.0.0_neutral__8wekyb3d8bbwe from the account of the current user.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

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

### -Package
Specifies an **AppxPackage** object or the full name of a package.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
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

### -PreserveApplicationData
{{Fill in description}}

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Windows.Appx.PackageManager.Commands.AppxPackage
An **AppxPackage** object that contain information, including the full name of the app package.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[PackageManager class](http://go.microsoft.com/fwlink/?LinkId=245447)

[Sideload Apps with DISM](http://go.microsoft.com/fwlink/?LinkID=231020)
