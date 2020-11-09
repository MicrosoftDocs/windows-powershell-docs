---
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: Appx
online version: 
schema: 2.0.0
title: Remove-AppxPackage
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 00607943-4ED6-4BFB-B2AF-B43BD542722C
---

# Remove-AppxPackage

## SYNOPSIS
Removes an app package (.appx) from a user account.

## SYNTAX

```
Remove-AppxPackage [-Package] <String> [-PreserveApplicationData] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AppxPackage** cmdlet removes an app package (.appx) from a user account.

## EXAMPLES

### Example 1
```
PS C:\>Remove-AppxPackage package1_1.0.0.0_neutral__8wekyb3d8bbwe
```

This command removes an app package named package1_1.0.0.0_neutral__8wekyb3d8bbwe from the account of the currently logged-on user.

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
Specifies an AppxPackage object or the full name of a package.

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

### -PreserveApplicationData
Specifies whether the application data should be preserved during the package removal.
The application data will then be available for later use.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Windows.Appx.PackageManager.Commands.AppxPackage
An AppxPackage object that contain information, including the full name of the app package.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Package Manager API](https://go.microsoft.com/fwlink/?LinkId=245447)

[How to Add and Remove Apps](https://go.microsoft.com/fwlink/?LinkID=231020)

[Get-AppxPackage](./Get-AppxPackage.md)

[Get-AppxPackageManifest](./Get-AppxPackageManifest.md)

[Add-AppxPackage](./Add-AppxPackage.md)

[Get-AppxLog](./Get-AppxLog.md)

[Get-AppxLastError](./Get-AppxLastError.md)

