---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-hostedemailaccount?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HostedEmailAccount
---

# Get-HostedEmailAccount

## SYNOPSIS
Gets the hosted email account that is assigned to a local user account.

## SYNTAX

```
Get-HostedEmailAccount [-LocalAccountName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-HostedEmailAccount** cmdlet gets the hosted email account that is assigned to a local user account.
A hosted email service provides a hosted email account.

## EXAMPLES

### Example 1: Get a hosted email account
```
PS C:\> Get-HostedEmailAccount -LocalAccountName "PattiFuller"
```

This command gets the hosted email account that is assigned to the local user account named PattiFuller.

### 1:
```
PS C:\>
```

## PARAMETERS

### -LocalAccountName
Specifies the name of a local Active Directory user account.
The cmdlet removes the hosted email account that is assigned to the local user account that you specify.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
LocalAccountName
Type: System.String
Description: local user name

## OUTPUTS

### EmailAccountInfo
This cmdlet returns the account information from the hosted email provider.

## NOTES

## RELATED LINKS

[Add-HostedEmailAccount](./Add-HostedEmailAccount.md)

[Set-HostedEmailAccount](./Set-HostedEmailAccount.md)

[Enable-HostedEmailAccount](./Enable-HostedEmailAccount.md)

[Disable-HostedEmailAccount](./Disable-HostedEmailAccount.md)

[Remove-HostedEmailAccount](./Remove-HostedEmailAccount.md)

[Clear-AssignedHostedEmailAccount](./Clear-AssignedHostedEmailAccount.md)

