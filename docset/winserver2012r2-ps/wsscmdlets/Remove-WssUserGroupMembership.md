---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/remove-wssusergroupmembership?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WssUserGroupMembership
---

# Remove-WssUserGroupMembership

## SYNOPSIS
Removes a user from a user group.

## SYNTAX

```
Remove-WssUserGroupMembership -GroupName <String> -UserName <String> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WssUserGroupMembership** cmdlet removes a user account from a user group.

## EXAMPLES

### Example 1: Remove a user from a group
```
PS C:\> Remove-WssUserGroupMembership -GroupName "HRGroup" -UserName "EvanNarvaez"
```

This command removes the account named EvanNarvaez from the user group named HRGroup.

### 1:
```
PS C:\>
```

## PARAMETERS

### -GroupName
Specifies the name of a user group.
The cmdlet removes a user account from the group that you specify.

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

### -UserName
Specifies the name of a user account.
The cmdlet removes the account that you specify from a group.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssUserGroupMembership](./Add-WssUserGroupMembership.md)

