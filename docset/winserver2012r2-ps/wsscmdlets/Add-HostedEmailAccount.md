---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/add-hostedemailaccount?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-HostedEmailAccount
---

# Add-HostedEmailAccount

## SYNOPSIS
Creates a hosted email account and assigns it to a network user account.

## SYNTAX

```
Add-HostedEmailAccount [-LocalAccountName] <String> [-EmailAddress] <String> [[-Password] <SecureString>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-HostedEmailAccount** cmdlet creates a hosted email account and assigns it to a local user account.
A hosted email service provides a hosted email account.

## EXAMPLES

### Example 1: Create a hosted email account
```
PS C:\> $SecureString_pwd = ConvertTo-SecureString "P@ssW0rD!" -AsPlainText -Force
PS C:\> Add-HostedEmailAccount -LocalAccountName "PattiFuller" -EmailAddresses "PattiFuller@Constoso.com" -Password $SecureString_pwd
```

The first command creates a secure string password.

The second command creates a hosted email account named PattiFuller@Constoso.com and assigns it to a local user account named PattiFuller, using the password created in the previous command.

## PARAMETERS

### -EmailAddress
Specifies an email address for a hosted email account.
The cmdlet creates a hosted email account that has the email address that you specify.

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

### -LocalAccountName
Specifies the name of a local Active Directory user account.
The cmdlet assigns the hosted email account to the local user account that you specify.

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

### -Password
Specifies the password, as a secure string, for the hosted email account.
To obtain a secure string, use the ConvertTo-SecureStringhttps://go.microsoft.com/fwlink/?LinkID=113291 cmdlet.
For more information, type `Get-Help ConvertTo-SecureString`.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String,System.String,System.Security.SecureString
LocalAccountName
Type: System.String
Description: local user name

EmailAddress
Type: System.String
Description: email address account

Password
Type: System.Security.SecureString
Description: password for the email account

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-HostedEmailAccount](./Get-HostedEmailAccount.md)

[Set-HostedEmailAccount](./Set-HostedEmailAccount.md)

[Enable-HostedEmailAccount](./Enable-HostedEmailAccount.md)

[Disable-HostedEmailAccount](./Disable-HostedEmailAccount.md)

[Remove-HostedEmailAccount](./Remove-HostedEmailAccount.md)

[Clear-AssignedHostedEmailAccount](./Clear-AssignedHostedEmailAccount.md)

