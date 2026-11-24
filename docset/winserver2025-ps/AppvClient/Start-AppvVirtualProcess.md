---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: AppVClientCmdlets-help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/start-appvvirtualprocess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-AppvVirtualProcess
---

# Start-AppvVirtualProcess

## SYNOPSIS
Starts a virtual process.

## SYNTAX

### Default (Default)
```
Start-AppvVirtualProcess [-FilePath] <String> [[-ArgumentList] <String[]>] [-Credential <PSCredential>]
 [-WorkingDirectory <String>] [-LoadUserProfile] [-NoNewWindow] [-PassThru] [-RedirectStandardError <String>]
 [-RedirectStandardInput <String>] [-RedirectStandardOutput <String>] [-Wait] [-UseNewEnvironment]
 -AppvClientObject <Object> [<CommonParameters>]
```

### UseShellExecute
```
Start-AppvVirtualProcess [-FilePath] <String> [[-ArgumentList] <String[]>] [-WorkingDirectory <String>]
 [-PassThru] [-Verb <String>] [-Wait] [-WindowStyle <ProcessWindowStyle>] -AppvClientObject <Object>
 [<CommonParameters>]
```

## DESCRIPTION
The **Start-AppvVirtualProcess** cmdlet starts a new virtual process.

## EXAMPLES

### Example 1: Start a virtual process in a virtual environment of a package
```
PS C:\> $AppVObj = Get-AppvClientPackage -Name "MyPackage"
PS C:\> Start-AppvVirtualProcess -FilePath "C:\Calc.exe" -AppvClientObject $AppVObj
```

The first command gets the client package named MyPackage by using the **Get-AppvClientPackage** cmdlet.
The command stores the result in the $AppVObj variable.

The second command starts a new virtual process for Calc.exe in virtual environment of in $AppVObj.

### Example 2: Start a virtual process in a virtual environment of a connection group
```
PS C:\> $AppVObj = Get-AppvClientConnectionGroup -Name MyConnectionGroup
PS C:\> Start-AppvVirtualProcess -FilePath "C:\Calc.exe" -AppvClientObject $AppVObj
```

The first command gets the client package named MyPackage by using the **Get-AppvClientConnectionGroup** cmdlet.
The command stores the result in the $AppVObj variable.

The second command starts a new virtual process for Calc.exe in the virtual environment of in $AppVObj.

## PARAMETERS

### -AppvClientObject
Specifies an **AppvClientPackage** or **AppvClientConnectionGroup** object.

```yaml
Type: Object
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ArgumentList
Specifies the arguments to be passed into the virtual process.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the credential to start this process.

```yaml
Type: PSCredential
Parameter Sets: Default
Aliases: RunAs

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath
Specifies a file path.

```yaml
Type: String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadUserProfile
Indicates that the cmdlet loads a user profile for use with the process.

```yaml
Type: SwitchParameter
Parameter Sets: Default
Aliases: Lup

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoNewWindow
Indicates that the cmdlet attempts to keep the process in the same window instead of opening a new window.

```yaml
Type: SwitchParameter
Parameter Sets: Default
Aliases: nnw

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

### -RedirectStandardError
Redirects the stderr to the file specified.

```yaml
Type: String
Parameter Sets: Default
Aliases: RSE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectStandardInput
Takes the stdinput from the file specified.

```yaml
Type: String
Parameter Sets: Default
Aliases: RSI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectStandardOutput
Redirects the stdout to the file specified.

```yaml
Type: String
Parameter Sets: Default
Aliases: RSO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseNewEnvironment
Indicates that this cmdlet uses a new environment for the process.

```yaml
Type: SwitchParameter
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Verb
Specifies a verb for the process.

```yaml
Type: String
Parameter Sets: UseShellExecute
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait
Indicates that the cmdlet uses synchronous operation of the virtual process.
The cmdlet waits to exit until the virtual process exits.

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

### -WindowStyle
Specifies what to do without a Process Window Style.
The acceptable values for this parameter are:

- Normal.
Display the normal window.
- Hidden.
Launch a hidden window.
- Minimized.
Launch a minimized window.
- Maximized.
Launch a maximized window.

The default value is Normal.

```yaml
Type: ProcessWindowStyle
Parameter Sets: UseShellExecute
Aliases:
Accepted values: Normal, Hidden, Minimized, Maximized

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkingDirectory
Specifies working directory of the process.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AppvClientConnectionGroup](./Get-AppvClientConnectionGroup.md)

[Get-AppvClientPackage](./Get-AppvClientPackage.md)

[Get-AppvVirtualProcess](./Get-AppvVirtualProcess.md)

