---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
Module Name: UpdateServices
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/updateservices/set-wsusdynamiccategory?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WsusDynamicCategory
---

# Set-WsusDynamicCategory

## SYNOPSIS

Sets the synchronization status of a dynamic category.

## SYNTAX

### ByName

```powershell
Set-WsusDynamicCategory [-UpdateServer <IUpdateServer>] -Name <String>
 -DynamicCategoryType <DynamicCategoryType> -Status <WsusDynamicCategoryStatus> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByObject

```powershell
Set-WsusDynamicCategory [-UpdateServer <IUpdateServer>] [-Status <WsusDynamicCategoryStatus>]
 -InputObject <IDynamicCategory> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The **Set-WsusDynamicCategory** cmdlet sets the synchronization status of a dynamic category in a specified Windows Server Update Services (WSUS) server.

## EXAMPLES

### Example 1: Set the synchronization status of a dynamic category

```powershell
PS C:\> Get-WsusDynamicCategory -DynamicCategoryType Device -Name "PCI/Device07" | Set-WsusDynamicCategory -Status Blocked
```

This command gets a dynamic category from the local server by using the [Get-WsusDynamicCategory](./Get-WsusDynamicCategory.md) cmdlet. The command passes the dynamic category to the current cmdlet by using the pipeline operator. The current cmdlet sets the synchronization status to Blocked. This value means that no updates are synchronized for this dynamic category.

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

Specifies the type of the dynamic category that this cmdlet modifies. The acceptable values for this parameter are:

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

Specifies a dynamic category object. This cmdlet modifies the synchronization settings for the dynamic category that this parameter specifies. To obtain a dynamic category, use the **Get-WsusDynamicCategory** cmdlet.

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

Specifies the name of the dynamic category to modify.

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

### -Status

Specifies the update synchronization status for the dynamic category. The acceptable values for this parameter are:

- Blocked. No updates are being synchronized for this dynamic category.
- SyncUpdates. Updates are being synchronized for this dynamic category.

```yaml
Type: WsusDynamicCategoryStatus
Parameter Sets: ByName
Aliases:
Accepted values: Blocked, InventoryOnly, SyncUpdates

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: WsusDynamicCategoryStatus
Parameter Sets: ByObject
Aliases:
Accepted values: Blocked, InventoryOnly, SyncUpdates

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateServer

Specifies a WSUS server. This cmdlet modifies a dynamic category on the server that this parameter specifies. To obtain a server, use the [Get-WsusServer](./Get-WsusServer.md) cmdlet. If you do not specify a value for this parameter, the cmdlet modifies dynamic categories on the local server.

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

[Add-WsusDynamicCategory](./Add-WsusDynamicCategory.md)

[Get-WsusDynamicCategory](./Get-WsusDynamicCategory.md)

[Remove-WsusDynamicCategory](./Remove-WsusDynamicCategory.md)

[Get-WsusServer](./Get-WsusServer.md)
