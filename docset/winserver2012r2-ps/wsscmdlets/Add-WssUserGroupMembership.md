---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/add-wssusergroupmembership?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WssUserGroupMembership
---

# Add-WssUserGroupMembership

## SYNOPSIS
Adds a user account to a user group.

## SYNTAX

```
Add-WssUserGroupMembership -GroupName <String> -UserName <String> [<CommonParameters>]
```

## DESCRIPTION
The **Add-WssUserGroupMembership** cmdlet adds a user account to a user group.

## EXAMPLES

### Example 1: Add a user account to a user group
```
PS C:\> Add-WssUserGroupMembership -GroupName "Support" -UserName "PattiFuller"
```

This command adds the user account named PattiFuller to the user group named Support.

## PARAMETERS

### -GroupName
Specifies the name of a user group.
The cmdlet adds a user account to the group that you specify.

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
The cmdlet adds the account that you specify to a user group.

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

[Remove-WssUserGroupMembership](./Remove-WssUserGroupMembership.md)

