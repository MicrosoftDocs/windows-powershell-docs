---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.DeveloperLicense.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Unregister-WindowsDeveloperLicense
ms.reviewer:
ms.assetid: 2D3D3DD5-BA97-4613-BADE-609298A6229B
---

# Unregister-WindowsDeveloperLicense

## SYNOPSIS
Disables Developer Mode on the current computer.

## SYNTAX

```
Unregister-WindowsDeveloperLicense [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Unregister-WindowsDeveloperLicense** cmdlet disables Developer Mode on the current computer.
If a developer license exists on the current computer, this cmdlet also removes it.
If you disable Developer Mode, you can no longer install and test your apps by using Microsoft Visual Studio.
Any app that you deployed from Visual Studio no longer runs on the current computer.

You must have administrative credentials to disable Developer Mode.
For more information, see [Enable your device for development](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/dn706236.aspx) (https://msdn.microsoft.com/en-us/library/windows/apps/xaml/dn706236.aspx) in the Microsoft Developer Network library. If you have not enabled Developer Mode for the current computer, this cmdlet returns an error.

## EXAMPLES

### Example 1: Disable Developer Mode
```
PS C:\> Unregister-WindowsDeveloperLicense
```

This command disables Developer Mode for the current computer.
The cmdlet prompts you for confirmation before it disables Developer Mode.
To skip this prompt, specify the **Force** parameter.

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

### -Force
Disables Developer Mode without prompting you for confirmation.
By default, the cmdlet prompts you for confirmation before it proceeds.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable your device for development](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/dn706236.aspx)

[Get-WindowsDeveloperLicense](./Get-WindowsDeveloperLicense.md)

[Show-WindowsDeveloperLicenseRegistration](./Show-WindowsDeveloperLicenseRegistration.md)

