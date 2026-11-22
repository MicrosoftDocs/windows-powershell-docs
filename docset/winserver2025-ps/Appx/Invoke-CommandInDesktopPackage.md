---
description: A debugging tool that creates a new process in the context of a packaged app.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: Appx
ms.date: 05/15/2023
online version: https://learn.microsoft.com/powershell/module/appx/invoke-commandindesktoppackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-CommandInDesktopPackage
---

# Invoke-CommandInDesktopPackage

## SYNOPSIS
A debugging tool that creates a new process in the context of a packaged app.

## SYNTAX

```
Invoke-CommandInDesktopPackage [-PackageFamilyName] <String> [-AppId] <String>
 [-Command] <String> [[-Args] <String>] [-PreventBreakaway] [<CommonParameters>]
```

## DESCRIPTION

`Invoke-CommandInDesktopPackage` creates a new process in the context of the supplied
**PackageFamilyName** and **AppId**.

The created process will have the identity of the provided **AppId** and will have access to its
virtualized file system and registry (if any). The new process will have a token that's similar to,
but not identical to, a real **AppId** process.

The primary use-case of this command is to invoke debugging or troubleshooting tools in the context
of the packaged app to access its virtualized resources. For example, you can run the Registry
Editor to see virtualized registry keys, or Notepad to read virtualized files. See the important
note that follows on using tools such as the Registry Editor that require elevation.

No guarantees are made about the behavior of the created process, other than it having the package
identity and access to the package's virtualized resources. In particular, the new process will
_not_ be created in an AppContainer even if an **AppId** process would normally be created in an
AppContainer. Features such as Privacy Controls or other App Settings may or may not apply to the
new process. You shouldn't rely on any specific side-effects of using this command, as they're
undefined and subject to change.

## EXAMPLES

### Example 1: Invoke Notepad to read virtualized files

The following command invokes Notepad in the context of the `ContosoApp` app from the
`Contoso.MyApp` package. This allows you to access resources such as a log file or configuration
file stored in the app's virtualized filesystem.

```powershell
$params = @{
    AppId             = 'ContosoApp'
    PackageFamilyName = 'Contoso.MyApp_abcdefgh23456'
    Command           = 'notepad.exe'
}
Invoke-CommandInDesktopPackage @params
```

## PARAMETERS

### -AppId

**AppId** is the Application ID from the target package's manifest.

For example, `MyAppName` is the Application ID in this manifest snippet:

`<Application Id="MyAppName" ... />`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Args

Optional arguments to be passed to the new process. For example, `/foo /bar`.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Command

An executable to invoke, like `regedit.exe`.

Note that if the executable requires elevation (like `regedit`), you must call
`Invoke-CommandInDesktopPackage` from an already-elevated context. Calling
`Invoke-CommandInDesktopPackage` from a non-elevated context doesn't work as expected. The new
process is created without the package context, and the PowerShell command fails.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PackageFamilyName

The Package Family Name of the target package. You can retrieve this by calling
[Get-AppxPackage](./Get-AppxPackage.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PreventBreakaway

Causes all child processes of the invoked process to also be created in the context of the
**AppId**. By default, child processes are created without any context. This switch is useful for
running `cmd.exe` so that you can launch multiple other tools in the package context.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-AppxPackage](./Get-AppxPackage.md)
