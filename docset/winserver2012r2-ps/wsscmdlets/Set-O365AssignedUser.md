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
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-o365assigneduser?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-O365AssignedUser
---

# Set-O365AssignedUser

## SYNOPSIS
Assigns an office_365_2 account to a network user account.

## SYNTAX

```
Set-O365AssignedUser [-LocalAccountName] <String> [-O365AccountUPN] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-O365AssignedUser** cmdlet assigns an office_365_1 account to a network user account.

## EXAMPLES

### Example 1: Assign an Office 365 account to a local user account
```
PS C:\> Set-O365AssignedUser -LocalAccountName "PattiFuller" -O365AccountUPN "PattiFuller@contoso.onmicrosoft.com"
An Office 365 account was assigned to the user account.
```

This command assigns an office_365_2 account to a local user account named PattiFuller.

### 1:
```
PS C:\>
```

## PARAMETERS

### -LocalAccountName
Specifies the name of a local Active Directory user account.
The cmdlet assigns the office_365_2 account to the local user account that you specify for the **O365AccountUPN** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -O365AccountUPN
Specifies a user principal name (UPN).
The cmdlet assigns the office_365_2 account that you specify to the local user account that you specify for the **LocalAccountName** parameter.

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

### System.String,System.String
LocalAccountName
Type: System.String
Description: local user name

O365AccountUPN
Type: System.String
Description: user principal name

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-O365AssignedUser](./Get-O365AssignedUser.md)

[Clear-O365AssignedUser](./Clear-O365AssignedUser.md)

