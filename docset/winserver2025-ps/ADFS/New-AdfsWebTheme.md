---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/new-adfswebtheme?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-AdfsWebTheme
---

# New-AdfsWebTheme

## SYNOPSIS
Creates an AD FS web theme.

## SYNTAX

```
New-AdfsWebTheme -Name <String> [-SourceName <String>] [-StyleSheet <Hashtable[]>]
 [-RTLStyleSheetPath <String>] [-OnLoadScriptPath <String>] [-Logo <Hashtable[]>] [-Illustration <Hashtable[]>]
 [-AdditionalFileResource <Hashtable[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-AdfsWebTheme** cmdlet creates an Active Directory Federation Services (AD FS) web theme.
You can create an empty **AdfsWebTheme** object, or you can create an **AdfsWebTheme** object that is based on an existing theme.
If you start with an existing theme, the cmdlet copies its properties to the new object.
You can also specify properties for the AD FS web theme.

## EXAMPLES

### Example 1: Create a theme
```
PS C:\> New-AdfsWebTheme -Name "Theme01" -AdditionalFileResource @{Uri="/adfs/portal/Background.png";Path="C:\Background.png"} -Illustration @{Locale="";Path="C:\Illustration.png"} -Logo @{Locale="";Path="C:\Logo.png"} -RTLStyleSheetPath "C:\StyleSheet.css" -StyleSheet @{Locale="";Path="C:\StyleSheet.css"}
```

This command creates a theme named Theme01 that offers a customized sign-in experience.
The command uses standard Windows PowerShell® syntax to create hash tables.
For more information, type `Get-Help about_Hash_Tables`.
The command specifies an additional file resource, an illustration image, a logo, and a cascading style sheet.
The command specifies no value for **Locale** for any of these parameters, and, therefore, the illustration, logo, and style sheet all use the invariant locale.

### Example 2: Copy a theme
```
PS C:\> New-AdfsWebTheme -Name "Theme02" -SourceName "Default"
```

This command creates a theme named Theme02 and copies the existing theme, named Default, into the new theme.
You can modify the new theme by using the **Export-AdfsWebTheme** or **Set-AdfsWebTheme** cmdlet.

### Example 3: Create and modify a theme
```
PS C:\> New-AdfsWebTheme -Name "Theme03" -AdditionalFileResource @{Uri="/adfs/portal/Background.png";Path="C:\Background.png"} -Illustration @{Locale="en-us";Path="c:\Illustration.png"} -Logo @{Locale="en-us";Path="C:\Logo.png"} -RTLStyleSheetPath "C:\StyleSheet.css" -SourceName "Default" -StyleSheet @{Locale="en-us";Path="C:\StyleSheet.css"}
```

This command creates a theme named Theme03, based on an existing theme named Default.
The command specifies an additional file resource, an illustration image, a logo, and a cascading style sheet.
The cmdlet specifies a value of en-us for **Locale** for the illustration, logo, and style sheet.

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

### -Name
Specifies a name.
The cmdlet assigns the name that you specify to the new theme.

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

### -RTLStyleSheetPath
Specifies a file path to a right-to-left (RTL) style sheet.

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

### -SourceName
Specifies the name of an existing theme.
The cmdlet uses the theme that you specify as the basis for the new theme.

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

### Microsoft.IdentityServer.Management.Resources.AdfsWebTheme
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

[Remove-AdfsWebTheme](./Remove-AdfsWebTheme.md)

[Set-AdfsWebTheme](./Set-AdfsWebTheme.md)

