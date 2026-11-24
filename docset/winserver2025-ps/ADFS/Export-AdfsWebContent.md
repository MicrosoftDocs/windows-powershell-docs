---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/export-adfswebcontent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-AdfsWebContent
---

# Export-AdfsWebContent

## SYNOPSIS
Exports properties of all web content objects in a specific locale to a specified file.

## SYNTAX

```
Export-AdfsWebContent [[-Locale] <CultureInfo>] -FilePath <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Export-AdfsWebContent** cmdlet exports properties of all web content objects in a specific locale, including global and relying party web contents, to a specified file.
If you do not specify a locale, the cmdlet exports the web content of the invariant locale.
The **Set-AdfsGlobalWebContent** and **Set-AdfsRelyingPartyWebContent** cmdlets add customized web content.

Use this cmdlet to implement localization of custom messages for the Active Directory Federation Services (AD FS) sign-in experience.
Export the web content to a .resx file, localize the file, and then import the localized .resx file by using the **Import-AdfsWebContent** cmdlet.

## EXAMPLES

### Example 1: Export web content for the invariant locale
```
PS C:\> Export-AdfsWebContent -FilePath "C:\WebContent\Invariant.resx"
```

This command exports all the customized web content for the invariant locale to the specified file.

### Example 2: Export web content for a specified locale
```
PS C:\> Export-AdfsWebContent -Locale en-us -FilePath "C:\WebContent\EnUs.resx"
```

This command exports all the customized web content for the en-us locale to the specified file.

## PARAMETERS

### -FilePath
Specifies a file path.
The cmdlet exports properties of web content objects to the file that you specify.

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
The cmdlet exports properties of web content objects for the local that you specify.

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

[Import-AdfsWebContent](./Import-AdfsWebContent.md)

