---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
keywords: powershell, cmdlet
ms.assetid: 3868A1B3-C617-4FB4-99D6-20AD636FB487
manager: dansimp
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Reset-IISServerManager
ms.author: v-kaunu
ms.reviewer:
---

# Reset-IISServerManager

## SYNOPSIS
Resets the IISAdministration view of the IIS ServerManager.

## SYNTAX

```
Reset-IISServerManager [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Reset-IISServerManager** cmdlet resets the IISAdministration view of the IIS ServerManager object and the view of .config file applicationHost.config to the current contents of the .config file.

## EXAMPLES

### Example 1: Reset the IISServerManager view of the configuration
```
PS C:\> $Sites = (Get-IISServerManager).Sites
PS C:\> $Sites["default web site"].Attributes["serverAutoStart"]


IsInheritedFromDefaultValue : True
IsProtected                 : False
Name                        : serverAutoStart
Schema                      : Microsoft.Web.Administration.ConfigurationAttributeSchema
Value                       : True


PS C:\> $Sites["default web site"].Attributes["serverAutoStart"].value = $false
PS C:\> $Sites["default web site"].Attributes["serverAutoStart"]


IsInheritedFromDefaultValue : False
IsProtected                 : False
Name                        : serverAutoStart
Schema                      : Microsoft.Web.Administration.ConfigurationAttributeSchema
Value                       : False


PS C:\> Reset-IISServerManager

Confirm
Are you sure you want to perform this action?
Performing the operation "Reset-IISServerManager" on target "ServerManager".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y
PS C:\> $Sites = (Get-IISServerManager).Sites
PS C:\> $Sites["default web site"].Attributes["serverAutoStart"]


IsInheritedFromDefaultValue : True
IsProtected                 : False
Name                        : serverAutoStart
Schema                      : Microsoft.Web.Administration.ConfigurationAttributeSchema
Value                       : True
```

This command resets the IISServerManager view of the .config file after changes are made, and then demonstrates that the changed value is restored.

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

[Get-IISServerManager](./Get-IISServerManager.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

