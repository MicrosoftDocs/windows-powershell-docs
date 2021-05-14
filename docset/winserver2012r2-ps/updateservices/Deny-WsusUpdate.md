---
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
Module Name: UpdateServices
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/updateservices/deny-wsusupdate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Deny-WsusUpdate
---

# Deny-WsusUpdate

## SYNOPSIS
Declines the update for deployment.

## SYNTAX

```
Deny-WsusUpdate -Update <WsusUpdate> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Deny-WsusUpdate** cmdlet declines the specified cmdlet for deployment.
To use this cmdlet, run the Get-WsusUpdate cmdlet and pipe the resulting WsusUpdate object into this cmdlet.
This operation requires Windows Server Update Services (WSUS) Administrator privileges.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-WsusUpdate -Classification All -Approval Unapproved -Status FailedOrNeeded | Deny-WsusUpdate
```

This example declines all unapproved updates with a status of failed or needed.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.UpdateServices.Commands.WsusUpdate
WsusUpdate

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-WsusUpdate](./Get-WsusUpdate.md)

