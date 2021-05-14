---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/adfs/export-adfswebtheme?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-AdfsWebTheme
---

# Export-AdfsWebTheme

## SYNOPSIS
Exports a web theme to a folder.

## SYNTAX

### IdentifierName
```
Export-AdfsWebTheme -Name <String> -DirectoryPath <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierObject
```
Export-AdfsWebTheme -WebTheme <AdfsWebTheme> -DirectoryPath <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Export-AdfsWebTheme** cmdlet exports a web theme object to a folder.
The cmdlet creates necessary folders that correspond to the web theme settings.
Use this cmdlet to create web themes based on existing themes, such as the default theme available with Active Directory Federation Services (AD FS).

## EXAMPLES

### Example 1: Export a web theme
```
PS C:\> Export-AdfsWebTheme -Name "Theme01" -DirectoryPath "C:\WebTheme"
```

This command exports a web theme named Theme01 to the folder C:\WebTheme.
The command places all files, including cascading style sheets, JavaScript files, and images, in folders in the specified folder.

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

### -DirectoryPath
Specifies the path of a folder.
The cmdlet exports the web theme to the folder that you specify.

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

### -Name
Specifies a name.
The cmdlet exports the web theme that has the name that you specify.

```yaml
Type: String
Parameter Sets: IdentifierName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WebTheme
Specifies an **AdfsWebTheme** object.
The cmdlet exports the theme that you specify.
To obtain an **AdfsWebTheme** object, use the Get-AdfsWebTheme cmdlet.

```yaml
Type: AdfsWebTheme
Parameter Sets: IdentifierObject
Aliases: 

Required: True
Position: Named
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

[Get-AdfsWebTheme](./Get-AdfsWebTheme.md)

[New-AdfsWebTheme](./New-AdfsWebTheme.md)

[Remove-AdfsWebTheme](./Remove-AdfsWebTheme.md)

[Set-AdfsWebTheme](./Set-AdfsWebTheme.md)

