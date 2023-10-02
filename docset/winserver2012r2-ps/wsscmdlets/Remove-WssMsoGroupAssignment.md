---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/remove-wssmsogroupassignment?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WssMsoGroupAssignment
---

# Remove-WssMsoGroupAssignment

## SYNOPSIS
Removes the assignment of a security group to a user group.

## SYNTAX

```
Remove-WssMsoGroupAssignment [-WssGroupName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WssMsoGroupAssignment** cmdlet removes the assignment of a aad_1 security group to a Windows Server Essentials user group.
This cmdlet does not remove the user group or the aad_2 security group.
After this cmdlet runs, the local group no longer syncs with the aad_2 group.
To remove a security group, use the Remove-WssMsoGroup cmdlet.

## EXAMPLES

### Example 1: Remove an assigned security group
```
PS C:\> Clear-WssMSOAssignedGroup -WssGroupName "AllEmployee"
```

This command removes the assignment to a security group for the user group named AllEmployee.

### 1:
```
PS C:\>
```

## PARAMETERS

### -WssGroupName
Specifies the name of a wseblue_2 user group.
The cmdlet removes the assignment of a security group for the user group that you specify.

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
WssGroupName
Type: System.String
Description: local network account name of group

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-WssMsoGroupAssignment](./Set-WssMsoGroupAssignment.md)

[Remove-WssMsoUserAssignment](./Remove-WssMsoUserAssignment.md)

