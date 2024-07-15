---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
Module Name: UpdateServices
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/updateservices/deny-wsusupdate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Deny-WsusUpdate
---

# Deny-WsusUpdate

## SYNOPSIS

Declines the update for deployment.

## SYNTAX

```powershell
Deny-WsusUpdate -Update <WsusUpdate> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The **Deny-WsusUpdate** cmdlet declines the specified cmdlet for deployment. To use this cmdlet, run the [Get-WsusUpdate](./Get-WsusUpdate.md) cmdlet and pass the resulting **WsusUpdate** object into this cmdlet. This operation requires Windows Server Update Services (WSUS) Administrator privileges.

## EXAMPLES

### Example 1: Deny updates

```powershell
PS C:\> Get-WsusUpdate -Classification All -Approval Unapproved -Status FailedOrNeeded | Deny-WsusUpdate
```

This command declines all unapproved updates with a status of failed or needed.

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

### Microsoft.UpdateServices.Commands.WsusUpdate

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Approve-WsusUpdate](./Approve-WsusUpdate.md)

[Get-WsusUpdate](./Get-WsusUpdate.md)
