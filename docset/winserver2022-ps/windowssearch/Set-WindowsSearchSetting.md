---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.WindowsSearch.Commands.dll-Help.xml
Module Name: WindowsSearch
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/windowssearch/set-windowssearchsetting?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WindowsSearchSetting
---

# Set-WindowsSearchSetting

## SYNOPSIS
Modifies values that control Windows Search.

## SYNTAX

```
Set-WindowsSearchSetting [-EnableWebResultsSetting <Boolean>] [-EnableMeteredWebResultsSetting <Boolean>]
 [-SearchExperienceSetting <String>] [-SafeSearchSetting <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WindowsSearchSetting** cmdlet modifies values that control Windows Search.
You can specify whether Windows Search displays web results or suggestions, and you can specify whether to display web results and suggestions while using a metered network.
You can specify whether Windows Search personalizes results, including whether Windows Search employs the specific location of the user.
You can also specify SafeSearch settings.

## EXAMPLES

### Example 1: Personalize Windows Search
```
PS C:\> Set-WindowsSearchSetting -SearchExperienceSetting "Personalized"
```

This command allows Windows Search to use search history, but not the specific location of the user, to personalize results.

### Example 2: Modify Windows Search settings
```
PS C:\> Set-WindowsSearchSetting -EnableWebResultsSetting $True -SafeSearchSetting "Strict" -SearchExperienceSetting "PersonalizedAndLocation"
```

This command modifies Windows Search settings.
The command enables the use of search history and the specific location of the user by specifying a value of PersonalizedAndLocation for the *SearchExperienceSetting* parameter.
The command enables web results and sets SafeSearch to a value of Strict.

### Example 3: Enable metered web search
```
PS C:\> Set-WindowsSearchSetting -EnableMeteredWebResultsSetting $True
```

This command enables Windows Search to display web results and suggestions while using metered connections.

## PARAMETERS

### -EnableMeteredWebResultsSetting
Indicates whether Windows Search displays web results and suggestions while using metered connections.
Specify a value of $True to display web results and suggestions over metered connections or a value of $False to exclude web results and suggestions.

Do not specify a value for this parameter if the value of the *EnableWebResultsSetting* parameter is $False.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -EnableWebResultsSetting
Indicates whether Windows Search displays web results and suggestions.
Specify a value of $True to display web results and suggestions or a value of $False to exclude web results and suggestions.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SafeSearchSetting
Specifies a SafeSearch setting for Window Search.

The acceptable values for this parameter are:

- Off.
Windows Search does not remove adult content from the results. 
- Moderate.
Windows Search excludes adult images and videos, but not text, from the results. 
- Strict.
Windows Search excludes adult images, videos, and text from the results.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Strict, Moderate, Off

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SearchExperienceSetting
Specifies a Windows Search experience setting.

The acceptable values for this parameter are:

- PersonalizedAndLocation.
Personalize Windows Search and other Microsoft experiences by using search history, some Microsoft account information, and specific location of the user. 
- Personalized.
Personalize Windows Search and other Microsoft experiences by using search history and some Microsoft account information, but do not use specific location of the user. 
- NotPersonalized.
Do not personalize Windows Search and other Microsoft experiences or use specific location of the user.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: PersonalizedAndLocation, Personalized, NotPersonalized

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WindowsSearchSetting](./Get-WindowsSearchSetting.md)

