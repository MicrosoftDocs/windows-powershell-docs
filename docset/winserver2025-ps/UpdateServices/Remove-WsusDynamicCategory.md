---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
Module Name: UpdateServices
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/updateservices/remove-wsusdynamiccategory?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WsusDynamicCategory
---

# Remove-WsusDynamicCategory

## SYNOPSIS

Removes a dynamic category from a WSUS server.

## SYNTAX

### ByObject

```powershell
Remove-WsusDynamicCategory [-UpdateServer <IUpdateServer>] -InputObject <IDynamicCategory> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByName

```powershell
Remove-WsusDynamicCategory [-UpdateServer <IUpdateServer>] -Name <String>
 -DynamicCategoryType <DynamicCategoryType> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The **Remove-WsusDynamicCategory** cmdlet removes a dynamic category from a Windows Server Update Services (WSUS) server.

## EXAMPLES

### Example 1: Remove a dynamic category

```powershell
PS C:\> Remove-WsusDynamicCategory -DynamicCategoryType Device -Name "PCI/Device07"
```

This command removes a dynamic category named PCI/Device07 of the Device type from the local update server.

## PARAMETERS

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DynamicCategoryType

Specifies the type of the dynamic category to remove. The acceptable values for this parameter are:

- ComputerModel
- Device
- Application

```yaml
Type: DynamicCategoryType
Parameter Sets: ByName
Aliases: Type
Accepted values: ComputerModel, Device, Application, Any

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Specifies a dynamic category object. This cmdlet removes the dynamic category that this parameter specifies. To obtain a dynamic category, use the [Get-WsusDynamicCategory](./Get-WsusDynamicCategory.md) cmdlet.

```yaml
Type: IDynamicCategory
Parameter Sets: ByObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Specifies the name of the dynamic category to remove.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateServer

Specifies a WSUS server. This cmdlet removes a dynamic category from the server that this parameter specifies. To obtain a server, use the [Get-WsusServer](./Get-WsusServer.md) cmdlet. If you do not specify a value for this parameter, the cmdlet removes dynamic categories from the local server.

```yaml
Type: IUpdateServer
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-WsusDynamicCategory](./Add-WsusDynamicCategory.md)

[Get-WsusDynamicCategory](./Get-WsusDynamicCategory.md)

[Set-WsusDynamicCategory](./Set-WsusDynamicCategory.md)
