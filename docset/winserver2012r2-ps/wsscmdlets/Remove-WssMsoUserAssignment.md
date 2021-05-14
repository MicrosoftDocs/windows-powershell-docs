---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/remove-wssmsouserassignment?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WssMsoUserAssignment
---

# Remove-WssMsoUserAssignment

## SYNOPSIS
Removes the assignment between an online service account and an account.

## SYNTAX

```
Remove-WssMsoUserAssignment [-WssUserName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WssMsoUserAssignment** cmdlet removes the online service account (the Microsoft account) from its assignment to a local network user account.
This cmdlet does not otherwise modify or delete either account.

## EXAMPLES

### Example 1: Remove an assignment
```
PS C:\> Remove-WssMsoUserAssignment -WssUserName "PattiFuller"
```

This command removes the assignment between the user account named PattiFuller and an online service account.

### 1:
```
PS C:\>
```

## PARAMETERS

### -WssUserName
Specifies the name of a user account.
The cmdlet removes the assignment to the online service account for the user account that you specify.

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
* Note: If you run this command against a local network user account that does not have a Microsoft account it generates an error.

## RELATED LINKS

[Set-WssMsoUserAssignment](./Set-WssMsoUserAssignment.md)

[Get-WssMsoAssignedUser](./Get-WssMsoAssignedUser.md)

[Remove-WssMsoGroupAssignment](./Remove-WssMsoGroupAssignment.md)

