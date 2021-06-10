---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Set-AppvClientMode
---

# Set-AppvClientMode

## SYNOPSIS
Sets the mode the client is running in.

## SYNTAX

### Normal
```
Set-AppvClientMode [-Normal] [<CommonParameters>]
```

### Uninstall
```
Set-AppvClientMode [-Uninstall] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AppvClientMode** cmdlet  sets the mode the client is running in.
By default, the cmdlet is set to *Normal* and the Microsoft Application Virtualization (App-V) Client runs normally.
If the *Uninstall* parameter is specified, the App-V Client prevents all client activity from happening which includes adding and publishing packages, along with creating virtual environments.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Normal
Indicates that the App-V Client functions normally.
This means all adding and publishing of App-V packages and creating of Virtual environments will function normally.

```yaml
Type: SwitchParameter
Parameter Sets: Normal
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Uninstall
Indicates that prevents the App-V Client from adding and publishing packages or creating any virtual environments.
This is set to enable an uninstall of the App-V Client to properly occur.

```yaml
Type: SwitchParameter
Parameter Sets: Uninstall
Aliases:

Required: True
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

[Get-AppvClientMode](./get-appvclientmode.md)
