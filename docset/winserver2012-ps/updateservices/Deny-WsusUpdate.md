---
external help file: WSUS_Cmdlets.xml
Module Name: UpdateServices
online version: https://learn.microsoft.com/powershell/module/updateservices/deny-wsusupdate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Deny-WsusUpdate

## SYNOPSIS
Declines the update for deployment.

## SYNTAX

```
Deny-WsusUpdate -Update <WsusUpdate> [-Confirm] [-WhatIf]
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

### Microsoft.UpdateServices.Commands.WsusUpdate
WsusUpdate

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-WsusUpdate](./Get-WsusUpdate.md)

