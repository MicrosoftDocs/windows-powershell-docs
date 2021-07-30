---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: Appx
ms.date: 05/19/2017
online version: https://docs.microsoft.com/powershell/module/appx/invoke-commandindesktoppackage?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-CommandInDesktopPackage
---

# Invoke-CommandInDesktopPackage

## SYNOPSIS
Runs a command in the context of a specified app package. 

## SYNTAX

```
Invoke-CommandInDesktopPackage [-PackageFamilyName] <String> [[-AppId] <String>] [-Command] <String>
 [[-Args] <String>] [-PreventBreakaway] [<CommonParameters>]
```

## DESCRIPTION
**Invoke-CommandInDesktopPackage** will have a package token and identity. It's primarily designed to be used as a debugging utility. 

## EXAMPLES

### Example 1: Invoke an executable from app package
```
PS C:\> Invoke-CommandInDesktopPackage -AppId "AppPackage1" -PackageFamilyName "29270sandstorm.AppPackage1_gah1vdar1nn7a" -Command "demo.exe"
```

This command invokes the demo.exe that can be found in '29270sandstorm.AppPackage1_gah1vdar1nn7a' app package under the 'AppPackage1' Application element. 

## PARAMETERS

### -AppId
AppId is the Application ID from the package manifest.



<Application Id="blah" ... />
</Application>

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Args
Optional arguments that should be passed to the Command (e.g. "/od")

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Command
An executable to invoke (e.g. "cmd.exe")

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PackageFamilyName
Family Name of the package. You can retrieve this by calling [Get-AppxPackage](./Get-AppxPackage.md).

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PreventBreakaway
Switch that causes the entire process tree to stay in the package context.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
System.Management.Automation.SwitchParameter

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-AppxPackage](./Get-AppxPackage.md)

