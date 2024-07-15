---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfswebtheme?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsWebTheme
---

# Set-AdfsWebTheme

## SYNOPSIS
Modifies properties of a web theme.

## SYNTAX

### IdentifierName (Default)
```
Set-AdfsWebTheme [-StyleSheet <Hashtable[]>] [-RTLStyleSheetPath <String>] [-OnLoadScriptPath <String>]
 [-Logo <Hashtable[]>] [-Illustration <Hashtable[]>] [-AdditionalFileResource <Hashtable[]>] [-PassThru]
 [-TargetName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierObject
```
Set-AdfsWebTheme [-StyleSheet <Hashtable[]>] [-RTLStyleSheetPath <String>] [-OnLoadScriptPath <String>]
 [-Logo <Hashtable[]>] [-Illustration <Hashtable[]>] [-AdditionalFileResource <Hashtable[]>] [-PassThru]
 [-TargetWebTheme] <AdfsWebTheme> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsWebTheme** cmdlet modifies properties of an **AdfsWebTheme** object.
Specify a web theme by name or by using the **Get-AdfsWebTheme** cmdlet.

## EXAMPLES

### Example 1: Modify a web named theme
```
PS C:\> Set-AdfsWebTheme -TargetName "Theme01" -Illustration @{Locale="";Path="c:\illustration.png"} -Logo @{Locale="";Path="c:\logo.png"} -RTLStyleSheetPath "C:\StyleSheet.css" -StyleSheet @{Locale="";Path="c:\stylesheet.css"}
```

This command modifies a web theme named Theme01.
The command uses standard Windows PowerShell® syntax to create hash tables.
For more information, type `Get-Help about_Hash_Tables`.
The command specifies an illustration image, a logo image, an RTL style sheet, and a cascading style sheet for Theme01.
The command specifies no value for **Locale** for any of these parameters, and, therefore, the illustration, logo, and style sheet all use the invariant locale.

### Example 2: Specify an additional resource
```
PS C:\> Set-AdfsWebTheme -TargetName "Theme02" -AdditionalFileResource @{Uri="/adfs/portal/Background.png";Path="Background.png"}
```

This command specifies an additional file resource for the web theme named Theme02.
The command makes a resource, in this case, BackGround.png, available to cascading style sheets or JavaScript applications.

### Example 3: Modify a web theme by using a variable
```
PS C:\> $Theme = Get-AdfsWebTheme -Name "Theme03"
PS C:\> Set-AdfsWebTheme -TargetWebTheme $Theme -Illustration @{Locale="";Path="C:\Illustration.png"} -Logo @{Locale="";Path="C:\Logo.png"} -RTLStyleSheetPath "C:\StyleSheet.css" -StyleSheet @{Locale="";Path="C:\StyleSheet.css"}
```

The first command uses the **Get-AdfsWebTheme** cmdlet to get the web theme named Theme03, and then stores it in the $Theme variable.

The second command modifies the web theme stored in the $Theme.
The command specifies an illustration image, a logo image, an RTL style sheet, and a cascading style sheet for that theme.

## PARAMETERS

### -AdditionalFileResource
Specifies an array of **Hashtable** objects that specify additional file resources by using two string keys: **Uri** and **Path**.
For more information, type `Get-Help about_Hash_Tables`.
**Uri** is the relative Uniform Resource Identifier (URI) string for a resource.
The URI always begins with /adfs/portal/.
**Path** is the file path of a resource.
If you do not specify the path, the cmdlet removes the file resource that corresponds to the specified URI.

Specify this parameter to make resources, such as images, available to cascading style sheets or JavaScript applications.

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

### -Illustration
Specifies an array of **Hashtable** objects that specify illustrations by using two string keys: **Locale** and **Path**.
**Locale** is a **CultureInfo** object.
**Path** is a file path.
If you do not specify a locale, **Locale** refers to the invariant locale.

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
Specifies an array of **Hashtable** objects that specify logos by using two string keys: **Locale** and **Path**.
**Locale** is a **CultureInfo** object.
**Path** is a file path.
If you do not specify a locale, **Locale** refers to the invariant locale.
If you do not specify a path, the cmdlet removes the file content that corresponds to the specified locale.

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
Specify this parameter to make resources, such as images, available to cascading style sheets or JavaScript applications.

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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -RTLStyleSheetPath
Specifies a file path to a run-time library (RTL) style sheet.

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
Specifies an array of **Hashtable** objects that specify style sheets by using two string keys: **Locale** and **Path**.
**Locale** is a **CultureInfo** object for a style sheet.
**Path** is a file path of the style sheet.
If you do not specify a locale, **Locale** refers to the invariant locale.
If you do not specify a path, the cmdlet removes the file content that corresponds to the specified locale.

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

### -TargetName
Specifies a name.
The cmdlet modifies the theme that you specify by name.

```yaml
Type: String
Parameter Sets: IdentifierName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetWebTheme
Specifies an **AdfsWebTheme** object.
The cmdlet modifies the theme that you specify.
To obtain an **AdfsWebTheme** object, use the **Get-AdfsWebTheme** cmdlet.

```yaml
Type: AdfsWebTheme
Parameter Sets: IdentifierObject
Aliases:

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

### System.IdentityServer.Management.Resources.AdfsWebTheme
This cmdlet generates a web customization object, **System.IdentityServer.Management.Resources.AdfsWebTheme**.
This object includes the following properties:

- Name: **System.String**
- IsBuiltinTheme: **System.Boolean**
- StyleSheet: **IDictionary\<string, byte\[\]\>**
- Logo: **IDictionary\<string, byte\[\]\>**
- Illustration: **IDictionary\<string, byte\[\]\>**
- RTLStyleSheet: **byte\[\]**
- AdditionalFileResources: **IDictionary\<string, byte\[\]\>**

## NOTES

## RELATED LINKS

[Export-AdfsWebTheme](./Export-AdfsWebTheme.md)

[Get-AdfsWebTheme](./Get-AdfsWebTheme.md)

[New-AdfsWebTheme](./New-AdfsWebTheme.md)

[Remove-AdfsWebTheme](./Remove-AdfsWebTheme.md)

