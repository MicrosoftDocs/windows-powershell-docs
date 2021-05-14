---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/enable-hostedemailaccount?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-HostedEmailAccount
---

# Enable-HostedEmailAccount

## SYNOPSIS
Enables the hosted email account assigned to a local user account.

## SYNTAX

```
Enable-HostedEmailAccount [-LocalAccountName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Enable-HostedEmailAccount** cmdlet enables a hosted email account that is assigned to a local user account.
A hosted email service provides a hosted email account.

## EXAMPLES

### Example 1: Enable a hosted email account
```
PS C:\> Enable-HostedEmailAccount -LocalAccountName "PattiFuller"
```

This command enables the hosted email account that is assigned to the local user account named PattiFuller.

### 1:
```
PS C:\>
```

## PARAMETERS

### -LocalAccountName
Specifies the name of a local Active Directory user account.
The cmdlet enables the hosted email account that is assigned to the local user account you specify.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
LocalAccountName

Type: System.String

Description: local user name

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-HostedEmailAccount](./Get-HostedEmailAccount.md)

[Add-HostedEmailAccount](./Add-HostedEmailAccount.md)

[Set-HostedEmailAccount](./Set-HostedEmailAccount.md)

[Disable-HostedEmailAccount](./Disable-HostedEmailAccount.md)

[Remove-HostedEmailAccount](./Remove-HostedEmailAccount.md)

[Clear-AssignedHostedEmailAccount](./Clear-AssignedHostedEmailAccount.md)

