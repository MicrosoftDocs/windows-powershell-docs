---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/UpdateServices/Approve-WsusUpdate?view=win10-ps
schema: 2.0.0
title: Approve-WsusUpdate
ms.reviewer:
ms.assetid: AF8E8258-D82E-43C1-BF9F-96DBA22E8B7F
---

# Approve-WsusUpdate

## SYNOPSIS

Approves an update to be applied to clients.

## SYNTAX

```powershell
Approve-WsusUpdate -Update <WsusUpdate> -Action <UpdateApprovalAction> -TargetGroupName <String> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The **Approve-WsusUpdate** cmdlet approves an update to be applied to clients. This operation requires Windows Server Update Services (WSUS) Administrator privileges.

To use this cmdlet, run the [Get-WsusUpdate](./Get-WsusUpdate.md) cmdlet and pipe the resulting **WsusUpdate** object into this cmdlet.

## EXAMPLES

### Example 1: Approve updates

```powershell
PS C:\> Get-WsusUpdate -Classification All -Approval Unapproved -Status FailedOrNeeded | Approve-WsusUpdate -Action Install -TargetGroupName "All Computers"
```

This command approves for installation all unapproved updates with a status of failed or needed.

## PARAMETERS

### -Action

Specifies the action that clients should perform when applying the associated update. The acceptable values for this parameter are:

- Install
- Not Approved
- Uninstall

```yaml
Type: UpdateApprovalAction
Parameter Sets: (All)
Aliases:
Accepted values: Install, Uninstall, NotApproved, All

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -TargetGroupName

Specifies the name of the computer target group for which to run this cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Update

Specifies the object that contains the server of the update to be approved or denied as well as the update to be approved or denied. This value is obtained by running the **Get-WsusUpdate** cmdlet and passing the resulting **WsusUpdate** object into this cmdlet.

```yaml
Type: WsusUpdate
Parameter Sets: (All)
Aliases:

Required: True
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft UpdateServices.Commands.WsusUpdate

## OUTPUTS

## NOTES

## RELATED LINKS

[Deny-WsusUpdate](./Deny-WsusUpdate.md)

[Get-WsusUpdate](./Get-WsusUpdate.md)
