---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/disable-exchangeintegration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ExchangeIntegration
---

# Disable-ExchangeIntegration

## SYNOPSIS
Disables on-premises Exchange Server Integration.

## SYNTAX

```
Disable-ExchangeIntegration [<CommonParameters>]
```

## DESCRIPTION
The **Disable-ExchangeIntegration** cmdlet disables integration of on-premises Microsoft Exchange Server Integration with the server that is running Windows Server Essentials.
Exchange Server preserves all the email accounts that you created  and all emails.
After you disable Exchange Server Integration, you can manage the email accounts and access the emails from the Exchange Management Console.

## EXAMPLES

### Example 1: Disable on-premises Exchange Server integration
```
PS C:\> Disable-ExchangeIntegration
```

This command disables integration of on-premises Exchange Server Integration.

### 1:
```
PS C:\>
```

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-ExchangeIntegration](./Enable-ExchangeIntegration.md)

