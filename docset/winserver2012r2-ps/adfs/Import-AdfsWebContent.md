---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Import-AdfsWebContent
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 3C03CB55-1E1B-40B3-84AE-655F2B7A33EB
---

# Import-AdfsWebContent

## SYNOPSIS
Imports properties from a resource file into global and relying party web content objects.

## SYNTAX

```
Import-AdfsWebContent [[-Locale] <CultureInfo>] -FilePath <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-AdfsWebContent** cmdlet imports properties from a .resx resource file into global and relying party web content objects.
If no corresponding web content object exists, the cmdlet creates an object.
If you do not specify a locale, the cmdlet imports web content for the invariant locale.

Use this cmdlet to implement localization of custom messages for the Active Directory Federation Services (AD FS) sign-in experience.
Export the web content by using the Export-AdfsWebContent cmdlet to a .resx file, localize the file, and then import the localized .resx file.

## EXAMPLES

### Example 1: Import web content for the invariant locale
```
PS C:\> Import-AdfsWebContent -FilePath "C:\WebContent\Invariant.resx"
```

This command imports the customized web content for the invariant locale into the AD FS configuration store from the specified file.

### Example 2: Import web content for a specified locale
```
PS C:\> Import-AdfsWebContent -Locale en-us -FilePath "C:\WebContent\EnUs.resx"
```

This command imports the customized web content for the en-us locale into the AD FS configuration store from the specified file.

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

### -FilePath
Specifies a file path.
The cmdlet imports properties from the file that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Locale
Specifies a locale.
The cmdlet imports properties of web content objects for the local that you specify.

```yaml
Type: CultureInfo
Parameter Sets: (All)
Aliases: 

Required: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Export-AdfsWebContent](./Export-AdfsWebContent.md)

