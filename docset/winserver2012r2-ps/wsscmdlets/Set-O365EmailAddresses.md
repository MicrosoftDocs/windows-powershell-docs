---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-o365emailaddresses?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-O365EmailAddresses
---

# Set-O365EmailAddresses

## SYNOPSIS
Sets up email addresses for a user.

## SYNTAX

```
Set-O365EmailAddresses [-LocalAccountName] <String>
 [[-EmailAddresses] <System.Collections.Generic.List`1[System.String]>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-O365EmailAddresses** cmdlet sets up email addresses in Exchange Online for a user from office_365_1 Integration.

## EXAMPLES

### Example 1: Set up email addresses for a user
```
PS C:\> Set-O365EmailAddresses -LocalAccountName "PattiFuller" -EmailAddresses "PattiFuller@Contoso.com,CustomerFeedback@Contoso.com"
```

This command sets up the specified email addresses for the user account named PattiFuller.

### 1:
```
PS C:\>
```

## PARAMETERS

### -EmailAddresses
Specifies the email addresses of the user that you specify in the **LocalAccountName** parameter.
The cmdlet sets up the email addresses that you specify.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LocalAccountName
Specifies the name of a local Active Directory user account.
The cmdlet sets up the email addresses in Exchange Online for the local user that you specify.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
LocalAccountName
Type: System.String
Description: local user name

### System.Collections.Generic.List<System.String>
EmailAddresses
Type: System.Collections.Generic.List<System.String>
Description: email addresses of the user

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-O365EmailAddresses](./Get-O365EmailAddresses.md)

