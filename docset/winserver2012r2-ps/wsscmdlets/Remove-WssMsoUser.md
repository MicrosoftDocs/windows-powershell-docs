---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/remove-wssmsouser?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WssMsoUser
---

# Remove-WssMsoUser

## SYNOPSIS
Removes an online service account.

## SYNTAX

```
Remove-WssMsoUser [-WssUserName] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WssMsoUser** cmdlet removes an online service account from aad_1.
Specify the name of the local network user account that the account is assigned to.

## EXAMPLES

### Example 1: Remove an online service account
```
PS C:\> Remove-WssMsoUser -WssUserName "EvanNarvaez"
```

This command removes the online service account that is assigned to the local network account named EvanNarvaez.

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

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
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

### -WssUserName
Specifies the name of a user account.
The cmdlet removes the online service account that is assigned to the account that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
WssUserName
Type: System.String
Description: local network account name of user

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssMsoUser](./Add-WssMsoUser.md)

[Disable-WssMsoUser](./Disable-WssMsoUser.md)

[Enable-WssMsoUser](./Enable-WssMsoUser.md)

[Get-WssMsoUser](./Get-WssMsoUser.md)

