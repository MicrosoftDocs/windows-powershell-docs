---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/clear-o365assigneduser?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-O365AssignedUser
---

# Clear-O365AssignedUser

## SYNOPSIS
Clears the assignment of an office_365_2 account to a local network user account.

## SYNTAX

```
Clear-O365AssignedUser [-LocalAccountName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Clear-O365AssignedUser** cmdlet clears the assignment of an office_365_1 account to a local user account.

## EXAMPLES

### Example 1 Clear the assignment of an office_365_2 account to a local user accountoffice_365_2
```
PS C:\> Clear-O365AssignedUser -LocalAccountName "PattiFuller"
```

This command clears the assignment of the office_365_2 account to the local network user account named PattiFuller.

### 1:
```
PS C:\>
```

## PARAMETERS

### -LocalAccountName
Specifies the name of a local Active Directory user account.
The cmdlet clears the assignment of the office_365_2 account to the local user account that you specify.

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

[Get-O365AssignedUser](./Get-O365AssignedUser.md)

[Set-O365AssignedUser](./Set-O365AssignedUser.md)

