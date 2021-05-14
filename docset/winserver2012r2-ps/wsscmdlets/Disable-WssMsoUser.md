---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/disable-wssmsouser?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WssMsoUser
---

# Disable-WssMsoUser

## SYNOPSIS
Disables an online service account.

## SYNTAX

```
Disable-WssMsoUser [-WssUserName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Disable-WssMsoUser** cmdlet disables the online service account that is assigned to a local user account.
This prevents the disabled account from using the online portal.

## EXAMPLES

### Example 1: Disable a Microsoft account
```
PS C:\> Disable-WssMsoUser -WssUserName "PattiFuller"
```

This command disables the online service account that is assigned to the user account named PattiFuller.

## PARAMETERS

### -WssUserName
Specifies the name of a user account.
The cmdlet disables the online service account that is assigned to the account that you specify.

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
WssUserName - local network account name of user.

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssMsoUser](./Add-WssMsoUser.md)

[Enable-WssMsoUser](./Enable-WssMsoUser.md)

[Get-WssMsoUser](./Get-WssMsoUser.md)

[Remove-WssMsoUser](./Remove-WssMsoUser.md)

