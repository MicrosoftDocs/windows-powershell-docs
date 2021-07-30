---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-o365subscriptioninfo?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-O365SubscriptionInfo
---

# Get-O365SubscriptionInfo

## SYNOPSIS
Gets the office_365_2 subscription information.

## SYNTAX

```
Get-O365SubscriptionInfo [<CommonParameters>]
```

## DESCRIPTION
The **Get-O365SubscriptionInfo** cmdlet gets the office_365_1 subscription information for the office_365_2 Integration Module.

## EXAMPLES

### Example 1: Get office_365_2 subscription information
```
PS C:\> Get-O365SubscriptionInfo
```

This command gets the office_365_2 subscription information for the Office 365 Integration Module.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.O365Integration.O365Information
This cmdlet returns a class that represents information of the office_365_2 company.
When output: office_365_2 integration is enabled
Activated Property System.Boolean
CompanyName Property System.String
TechnicalContact Property System.String
Address Property Microsoft.WindowsServerSolutions.O365Integration.Address
O365Skus Property System.Collections.ObjectModel.ReadOnlyCollection\<O365Sku\>
PrimaryDomain Property System.String
InitialDomain Property System.String

## NOTES

## RELATED LINKS

