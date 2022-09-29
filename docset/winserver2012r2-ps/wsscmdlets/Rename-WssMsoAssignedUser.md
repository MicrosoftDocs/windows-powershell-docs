---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/rename-wssmsoassigneduser?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-WssMsoAssignedUser
---

# Rename-WssMsoAssignedUser

## SYNOPSIS
Modifies the online service account for a user.

## SYNTAX

```
Rename-WssMsoAssignedUser [-WssUserName] <String> [-NewMsoUserName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Rename-WssMsoAssignedUser** cmdlet modifies the online service account assigned to a local network user account in aad_1.

## EXAMPLES

### Example 1: Modify a Microsoft account
```
PS C:\> Update-WssMSOAccountName -WssUserName "DavidChew" -NewMsoUserName "DavidChew@TSQA.Contoso.com"
```

This command modifies the online service account for the user account named DavidChew.

### 1:
```
PS C:\>
```

## PARAMETERS

### -NewMsoUserName
Specifies an online service account, as a user principal name (UPN).
The cmdlet assigns the UPN that you specify to the user that the **WssUserName** parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WssUserName
Specifies the name of a user account.
The cmdlet updates the online service account for the user account that you specify.

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

[Get-WssMsoAssignedUser](./Get-WssMsoAssignedUser.md)

