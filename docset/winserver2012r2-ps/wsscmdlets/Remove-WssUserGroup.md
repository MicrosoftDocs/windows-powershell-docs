---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/remove-wssusergroup?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WssUserGroup
---

# Remove-WssUserGroup

## SYNOPSIS
Removes a user group.

## SYNTAX

```
Remove-WssUserGroup -Name <String> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WssUserGroup** cmdlet removes a user group.
If you previously assigned a aad_1 security group to the group to remove, this cmdlet removes the assignment, but does not remove the security group.

## EXAMPLES

### Example 1: Remove a user group
```
PS C:\> Remove-WssUserGroup -Name "Support"
```

This command removes a user group named support, as well as the assignment to a security group, if one exists.

### 1:
```
PS C:\>
```

## PARAMETERS

### -Name
Specifies a name.
The cmdlet removes the user group that you specify by name.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssUserGroup](./Add-WssUserGroup.md)

[Get-WssUserGroup](./Get-WssUserGroup.md)

[Set-WssUserGroup](./Set-WssUserGroup.md)

