---
author: Kateyanne
external help file: WSUS_Cmdlets.xml
manager: dansimp
Module Name: UpdateServices
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/updateservices/approve-wsusupdate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Approve-WsusUpdate

## SYNOPSIS
Approves an update to be applied to clients.

## SYNTAX

```
Approve-WsusUpdate -Action <UpdateApprovalAction> -TargetGroupName <String> -Update <WsusUpdate> [-Confirm]
 [-WhatIf]
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

Required: True
Position: Named
Default value: None
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft UpdateServices.Commands.WsusUpdate
WsusUpdate

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WsusUpdate](./Get-WsusUpdate.md)

