---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ServerCore-help.xml
Module Name: ServerCore
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/servercore/set-displayresolution?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DisplayResolution
---

# Set-DisplayResolution

## SYNOPSIS
Changes the display resolution for a Server Core server.

## SYNTAX

```
Set-DisplayResolution [-Width] <Object> [-Height] <Object> [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DisplayResolution** cmdlet changes the display resolution for Windows Server® 2012 in Server Core mode.
Specify both the width and the height in pixels.
Unless you use the *Force* parameter, the cmdlet prompts you before it changes the settings.
You can use the Get-DisplayResolution cmdlet to view the current resolution.

For more information about Server Core mode, see [Configure and Manage Server Core Installations](https://technet.microsoft.com/en-us/library/jj574091).

## EXAMPLES

### Example 1: Set resolution
```
PS C:\> Set-DisplayResolution -Width 1920 -Height 1200
setres will now attempt to apply the following display settings:
  Width:          1920
  Height:         1200
Your screen may go blank for a moment. If your screen remains blank, press N
or restart your computer to revert the display settings.
Do you want to save the display settings?
[Y,N]?_
```

This command sets the display resolution to a width of 1920 pixels and a height of 1200 pixels.
The system prompts you for confirmation.

### Example 2: Set resolution without confirmation
```
PS C:\>Set-DisplayResolution -Width 1024 -Height 768 -Force
setres will now attempt to apply the following display settings:
  Width:          1024
  Height:         768
The new display settings have been saved.
```

This command sets the display resolution to a width of 1024 pixels and a height of 768 pixels.
Because the command uses the *Force* parameter, it makes the change without prompting you.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

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

### -Height
Specifies a height, in pixels, for the display.

```yaml
Type: Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Width
Specifies a width, in pixels, for the display.

```yaml
Type: Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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

[Get-DisplayResolution](./Get-DisplayResolution.md)

