---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsrelyingpartywebtheme?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsRelyingPartyWebTheme
---

# Set-AdfsRelyingPartyWebTheme

## SYNOPSIS
Applies a web theme to a relying party.

## SYNTAX

### IdentifierName (Default)
```
Set-AdfsRelyingPartyWebTheme [-StyleSheet <Hashtable[]>] [-RTLStyleSheetPath <String>]
 [-OnLoadScriptPath <String>] [-Logo <Hashtable[]>] [-Illustration <Hashtable[]>]
 [-SourceWebThemeName <String>] [-SourceRelyingPartyName <String>] [-TargetRelyingPartyName] <String> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### IdentifierObject
```
Set-AdfsRelyingPartyWebTheme [-StyleSheet <Hashtable[]>] [-RTLStyleSheetPath <String>]
 [-OnLoadScriptPath <String>] [-Logo <Hashtable[]>] [-Illustration <Hashtable[]>]
 [-SourceWebThemeName <String>] [-SourceRelyingPartyName <String>]
 [-TargetRelyingPartyWebTheme] <AdfsRelyingPartyWebTheme> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsRelyingPartyWebTheme** cmdlet applies a web theme to a relying party.
A web theme includes logo, illustration, stylesheets, and custom onload.js files.

## EXAMPLES

### Example 1: Create a custom theme and assign it to the Office 365 relying party trust
```
PS C:\> New-AdfsWebTheme -Name "Office365Theme" -SourceName "default"
PS C:\> Set-AdfsWebTheme -TargetName "Office365Theme" -Illustration @{Path="C:\localpath\illustration22.jpg"}
PS C:\> Set-AdfsRelyingPartyWebTheme -TargetRelyingPartyName "Microsoft Office 365 Identity Platform" -SourceWebThemeName "Office365Theme"
```

The first command creates an AD FS web theme by using the **New-AdfsWebTheme** cmdlet.
The theme is named Office365Theme.

The second command modifies Office365Theme by using the **Set-AdfsWebTheme** cmdlet.

The final command assigns the custom theme to the Office 365 relying party trust.

### Example 2: Create an advanced per application custom theme and assign it to a relying party
```
PS C:\> New-AdfsWebTheme -Name "AppSpecificTheme" -SourceName "default"
PS C:\> Export-AdfsWebTheme -Name "AppSpecificTheme" -DirectoryPath "C:\AppSpecificTheme"
PS C:\> Set-AdfsWebTheme -TargetName "AppSpecificTheme" -AdditionalFileResource @{Uri='/adfs/portal/script/onload.js';Path="C:\AppSpecificTheme\script\onload.js"}
PS C:\> Set-AdfsRelyingPartyWebTheme -TargetRelyingPartyName "urn:app1" -SourceWebThemeName "AppSpecificTheme"
```

The first command creates a theme as a copy of the default global theme in AD FS by using **New-AdfsWebTheme**.

The second command exports the theme for customization by using the **Export-AdfsWebTheme** cmdlet.

The third command customizes the theme by specifying files by using **Set-AdfsWebTheme**.

The final command applies the customized theme to a relying party.

## PARAMETERS

### -Illustration
Specifies an illustration as a hash table.

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Logo
Specifies a logo as a hash table.

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnLoadScriptPath
Specifies the path of an onload script.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RTLStyleSheetPath
Specifies the path of the RTL style sheet.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceRelyingPartyName
Specifies the name of the source relying party.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceWebThemeName
Specifies the name of the source web theme.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StyleSheet
Specifies a style sheet as a hash table.

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetRelyingPartyName
Specifies the name of the target relying party.

```yaml
Type: String
Parameter Sets: IdentifierName
Aliases: Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetRelyingPartyWebTheme
Specifies the name of the target web theme.

```yaml
Type: AdfsRelyingPartyWebTheme
Parameter Sets: IdentifierObject
Aliases: TargetWebTheme

Required: True
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

[Export-AdfsWebTheme](./Export-AdfsWebTheme.md)

[Get-AdfsRelyingPartyWebTheme](./Get-AdfsRelyingPartyWebTheme.md)

[New-AdfsWebTheme](./New-AdfsWebTheme.md)

[Remove-AdfsRelyingPartyWebTheme](./Remove-AdfsRelyingPartyWebTheme.md)

[Set-AdfsWebTheme](./Set-AdfsWebTheme.md)

