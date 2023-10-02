---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/get-wssmsouser?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssMsoUser
---

# Get-WssMsoUser

## SYNOPSIS
Gets the online service account for a user.

## SYNTAX

```
Get-WssMsoUser [[-MsoUserName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssMsoUser** cmdlet gets the online service account for a user principal name (UPN) from aad_1.
If you do not specify a UPN, the cmdlet gets all online service accounts.

## EXAMPLES

### Example 1: Get an online service account
```
PS C:\> Get-WssMsoUser -MsoUserName "DavidChew@TSQA.Contoso.com"
```

This command gets the online service account for the specified UPN.

## PARAMETERS

### -MsoUserName
Specifies a UPN.
The cmdlet gets the online service account for the UPN that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

[Add-WssMsoUser](./Add-WssMsoUser.md)

[Disable-WssMsoUser](./Disable-WssMsoUser.md)

[Enable-WssMsoUser](./Enable-WssMsoUser.md)

[Remove-WssMsoUser](./Remove-WssMsoUser.md)

