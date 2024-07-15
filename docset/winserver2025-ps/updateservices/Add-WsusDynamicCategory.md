---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
Module Name: UpdateServices
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/updateservices/add-wsusdynamiccategory?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WsusDynamicCategory
---

# Add-WsusDynamicCategory

## SYNOPSIS

Adds a dynamic category to a WSUS server.

## SYNTAX

### ByObject

```powershell
Add-WsusDynamicCategory [-UpdateServer <IUpdateServer>] -InputObject <IDynamicCategory> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByName

```powershell
Add-WsusDynamicCategory [-UpdateServer <IUpdateServer>] -Name <String>
 -DynamicCategoryType <DynamicCategoryType> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The **Add-WsusDynamicCategory** cmdlet adds a dynamic category to a Windows Server Update Services (WSUS) server.

In order to transfer dynamic categories from one update server to another, pass the results of the Get-WsusDynamicCategory cmdlet to the current cmdlet by using the pipeline operator.

This cmdlet is used to add Dynamic Categories to WSUS, based on the type of requirement (computer model, device or application). The definition of Dynamic Categories in a WSUS implementation helps to categorize the applying of updates to the different categories available.

In some cases, you need advanced automation when using Dynamic Categories. If you want to download a specific device driver for a specific group of computers in the physical network, for example, advanced automation is required to use Dynamic Categories. In this case, the use of [Microsoft Endpoint Configuration Manager](/configmgr/) is needed to [install and configure a software update point](/configmgr/sum/get-started/install-a-software-update-point) feature.

## EXAMPLES

### Example 1: Add a dynamic category to the local WSUS server

```text
PS C:\> Add-WsusDynamicCategory -DynamicCategoryType Device -Name "PCI/Device07"
Name                                     Type                                     Status
----                                     ----                                     ------
PCI/Device07                             Device                                   True
```

This command adds a dynamic category named PCI/Device07 the local update server. The command specifies that they type is Device.

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

Specifies the type of the dynamic category to add. The acceptable values for this parameter are:

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

Specifies the dynamic category object that this cmdlet adds to the server. To obtain a dynamic category, use the [Get-WsusDynamicCategory](./Get-WsusDynamicCategory.md) cmdlet.

```yaml
Type: IDynamicCategory
Parameter Sets: ByObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Specifies the name of the dynamic category to add.

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

Specifies the WSUS server to which this cmdlet adds the dynamic category. To obtain a server, use the [Get-WsusServer](./Get-WsusServer.md) cmdlet. If you do not specify a value for this parameter, the cmdlet adds the dynamic category to the local server.

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

### Microsoft.UpdateServices.Administration.IDynamicCategory

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-WsusDynamicCategory](./Get-WsusDynamicCategory.md)

[Remove-WsusDynamicCategory](./Remove-WsusDynamicCategory.md)

[Set-WsusDynamicCategory](./Set-WsusDynamicCategory.md)

[Get-WsusServer](./Get-WsusServer.md)
