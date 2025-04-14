---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
Module Name: UpdateServices
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/updateservices/get-wsusdynamiccategory?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WsusDynamicCategory
---

# Get-WsusDynamicCategory

## SYNOPSIS

Gets dynamic categories on a WSUS server.

## SYNTAX

### Filter (Default)

```powershell
Get-WsusDynamicCategory [-UpdateServer <IUpdateServer>] [-DynamicCategoryTypeFilter <DynamicCategoryType>]
 [-First <Int64>] [-Skip <Int64>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByName

```powershell
Get-WsusDynamicCategory [-UpdateServer <IUpdateServer>] -DynamicCategoryType <DynamicCategoryType>
 -Name <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The **Get-WsusDynamicCategory** cmdlet gets dynamic categories on a Windows Server Update Services (WSUS) server.

## EXAMPLES

### Example 1: Get all dynamic categories for specified servers

```text
PS C:\> Get-WsusServer | Get-WsusDynamicCategory
Name                                     Type                                     Status
----                                     ----                                     ------
5d6a452a-55ba-4e11-adac-85e180bda3d6     ComputerModel                            True
PCI/Device07                             Device                                   True
```

This command gets all dynamic categories from the current update server by using the [Get-WsusServer](./Get-WsusServer.md) cmdlet. The command passes the server to the current cmdlet by using the pipeline operator. The current cmdlet gets the available dynamic categories for the update server.

### Example 2: Get a named dynamic category

```text
PS C:\> Get-WsusDynamicCategory -DynamicCategoryType Device -Name "PCI/Device07"
Name                                     Type                                     Status
----                                     ----                                     ------
PCI/Device07                             Device                                   True
```

This command gets the dynamic category named PCI/Device07 that is a Device type.

### Example 3: Get dynamic categories by type

```text
PS C:\> Get-WsusDynamicCategory -DynamicCategoryTypeFilter ComputerModel
Name                                     Type                                     Status
----                                     ----                                     ------
5d6a452a-55ba-4e11-adac-85e180bda3d6     ComputerModel                            True
```

This command gets dynamic categories of the type ComputerModel that are currently available on the local server.

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

Specifies the type of the dynamic category. The acceptable values for this parameter are:

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

### -DynamicCategoryTypeFilter

Specifies the type of the dynamic categories that this cmdlet gets. The possible values are the same as those of the _DynamicCategoryType_ parameter.

```yaml
Type: DynamicCategoryType
Parameter Sets: Filter
Aliases: TypeFilter
Accepted values: ComputerModel, Device, Application, Any

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -First

Specifies the number of dynamic categories to return from the beginning of the results.

```yaml
Type: Int64
Parameter Sets: Filter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Specifies the name of the dynamic category to get.

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

### -Skip

Specifies the number of dynamic categories to skip from the beginning of the results.

```yaml
Type: Int64
Parameter Sets: Filter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateServer

Specifies a WSUS server. This cmdlet gets dynamic categories on the server that this parameter specifies. To obtain a server, use the Get-WsusServer cmdlet. If you do not specify a value for this parameter, the cmdlet gets dynamic category from the local server.

```yaml
Type: IUpdateServer
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.UpdateServices.Administration.IUpdateServer

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-WsusDynamicCategory](./Add-WsusDynamicCategory.md)

[Remove-WsusDynamicCategory](./Remove-WsusDynamicCategory.md)

[Set-WsusDynamicCategory](./Set-WsusDynamicCategory.md)

[Get-WsusServer](./Get-WsusServer.md)
