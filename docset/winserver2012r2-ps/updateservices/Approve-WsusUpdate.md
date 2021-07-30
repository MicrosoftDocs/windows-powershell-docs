---
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
Module Name: UpdateServices
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/updateservices/approve-wsusupdate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Approve-WsusUpdate
---

# Approve-WsusUpdate

## SYNOPSIS
Approves an update to be applied to clients.

## SYNTAX

```
Approve-WsusUpdate -Update <WsusUpdate> -Action <UpdateApprovalAction> -TargetGroupName <String> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Approve-WsusUpdate** cmdlet is used to approve an update to be applied to clients.
This operation requires Server Update Services (WSUS) Administrator privileges.

To use this cmdlet, run the Get-WsusUpdate cmdlet and pipe the resulting WsusUpdate object into this cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-WsusUpdate -Classification All -Approval Unapproved -Status FailedOrNeeded | Approve-WsusUpdate -Action Install -TargetGroupName "All Computers"
```

This example approves for installation all unapproved updates with a status of failed or needed.

## PARAMETERS

### -Action
Specifies the action that clients should perform when applying the associated update.
The acceptable values for this parameter are:

 -- Install 

 -- Not Approved 

 -- Uninstall

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
Specifies the object that contains the server of the update to be approved or denied as well as the update to be approved or denied.
This value is obtained by running the Get-WsusUpdate cmdlet and piping the resulting WsusUpdate object into this cmdlet.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft UpdateServices.Commands.WsusUpdate
WsusUpdate

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WsusUpdate](./Get-WsusUpdate.md)

