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
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssmsouserassignment?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WssMsoUserAssignment
---

# Set-WssMsoUserAssignment

## SYNOPSIS
Assigns an online service account to a user account.

## SYNTAX

```
Set-WssMsoUserAssignment [-WssUserName] <String> [-MsoUserName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssMsoUserAssignment** cmdlet assigns an online service account to a local network user account.

## EXAMPLES

### Example 1: Assign an online service account
```
PS C:\> Set-WssMSOAssignedUser -WssUserName "Admin" -MsoUserName "DavidChew@TSQA.Contoso.com"
```

This command assigns the online service account DavidChew@TSQA.Contoso.com to the local network user account named Admin.

### 1:
```
PS C:\>
```

## PARAMETERS

### -MsoUserName
Specifies a user principal name (UPN).
The cmdlet assigns the online service account for the UPN that you specify to a user account.

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
The cmdlet assigns the online service account to the user account that you specify.

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

###  
WssUserName
Type: System.String
Description: local network account name of user

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-WssMsoUserAssignment](./Remove-WssMsoUserAssignment.md)

[Get-WssMsoAssignedUser](./Get-WssMsoAssignedUser.md)

[Rename-WssMsoAssignedUser](./Rename-WssMsoAssignedUser.md)

[Set-WssMsoGroupAssignment](./Set-WssMsoGroupAssignment.md)

