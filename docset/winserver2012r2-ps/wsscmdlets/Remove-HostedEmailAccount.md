---
author: Kateyanne
description: 
external help file: WssCmdlets.dll-Help.xml
manager: jasgro
Module Name: WSSCmdlets
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/remove-hostedemailaccount?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HostedEmailAccount
---

# Remove-HostedEmailAccount

## SYNOPSIS
Removes the hosted email account assigned to a local user account.

## SYNTAX

```
Remove-HostedEmailAccount [-LocalAccountName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HostedEmailAccount** cmdlet removes the hosted email account that is assigned to a local user account.
The cmdlet removes the hosted email account from Windows Server Essentials that is provided by a hosted email service.

## EXAMPLES

### Example 1: Removes a hosted email account
```
PS C:\> Remove-HostedEmailAccount -LocalAccountName "PattiFuller"
```

This command removes the hosted email account that is assigned to the local user account named PattiFuller.

### 1:
```
PS C:\>
```

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

### -LocalAccountName
Specifies the name of a local Active Directory user account.
The cmdlet removes the hosted email account that is assigned to the local user account that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

### System.String
LocalAccountName
Type: System.String
Description: local user name

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-HostedEmailAccount](./Get-HostedEmailAccount.md)

[Add-HostedEmailAccount](./Add-HostedEmailAccount.md)

[Set-HostedEmailAccount](./Set-HostedEmailAccount.md)

[Enable-HostedEmailAccount](./Enable-HostedEmailAccount.md)

[Disable-HostedEmailAccount](./Disable-HostedEmailAccount.md)

[Clear-AssignedHostedEmailAccount](./Clear-AssignedHostedEmailAccount.md)

