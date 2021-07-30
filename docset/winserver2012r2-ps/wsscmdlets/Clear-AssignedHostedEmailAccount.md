---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/clear-assignedhostedemailaccount?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-AssignedHostedEmailAccount
---

# Clear-AssignedHostedEmailAccount

## SYNOPSIS
Removes the relationship between a hosted email account and a local user account.

## SYNTAX

```
Clear-AssignedHostedEmailAccount [-LocalAccountName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Clear-AssignedHostedEmailAccount** cmdlet removes the relationship between a hosted email account and the local user account to which the hosted email account is assigned.
A hosted email service provides a hosted email account.

## EXAMPLES

### Example 1: Remove the relationship between a hosted email account and a local user account
```
PS C:\> Clear-AssignedHostedEmailAccount -LocalAccountName "PattiFuller"
```

This command removes the relationship between the hosted email account and the local user account named PattiFuller.

### 1:
```
PS C:\>
```

## PARAMETERS

### -LocalAccountName
Specifies the name of a local Active Directory user account.
The cmdlet removes the relationship between the hosted email account and the local user account that you specify.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-HostedEmailAccount](./Get-HostedEmailAccount.md)

