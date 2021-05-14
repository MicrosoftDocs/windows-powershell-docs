---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/remove-wssmsogroup?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WssMsoGroup
---

# Remove-WssMsoGroup

## SYNOPSIS
Removes a security group that is assigned to a user group.

## SYNTAX

```
Remove-WssMsoGroup [-WssGroupName] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WssMsoGroup** cmdlet removes a Windows aad_1 security group that is assigned to a Windows Server Essentials user group.
This cmdlet removes both the assignment and the security group itself from aad_2.
To remove just the assignment, use the Remove-WssMsoGroupAssignment cmdlet.
If the group that is specified is not assigned to a Windows Server Essentials user group, no error is generated, but nothing is done to the group.

## EXAMPLES

### Example 1: Remove a security group
```
PS C:\> Remove-WssMSOGroup -WssGroupName "Admins"
```

This command removes the security group assigned to the user group named Admins.

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

### -WssGroupName
Specifies the name of a wseblue_2 user group.
The cmdlet removes the security group assigned to the user group that you specify.

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

[Add-WssMsoGroup](./Add-WssMsoGroup.md)

[Get-WssMsoGroup](./Get-WssMsoGroup.md)

[Remove-WssMsoGroupAssignment](./Remove-WssMsoGroupAssignment.md)

