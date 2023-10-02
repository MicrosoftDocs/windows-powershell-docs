---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/get-o365domainconfiguration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-O365DomainConfiguration
---

# Get-O365DomainConfiguration

## SYNOPSIS
Gets the office_365_2 domain configuration.

## SYNTAX

```
Get-O365DomainConfiguration [<CommonParameters>]
```

## DESCRIPTION
The **Get-O365DomainConfiguration** cmdlet gets the domain configuration for office_365_1.

## EXAMPLES

### Example 1: Get the domain configuration
```
PS C:\> Get-O365DomainConfiguration
```

This command gets the domain configuration for office_365_2.

### 1:
```
PS C:\>
```

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.O365Integration.O365DomainConfiguration
This cmdlet returns a class that represents the domain configuration for office_365_2
When output: office_365_2 integration is enabled
AvailableDomains Property System.Collections.ObjectModel.ReadOnlyCollection\<O365Domain\>
PrimaryDomainName Property System.String
CustomDomainName Property System.String
CustomDomainStatus Property Microsoft.WindowsServerSolutions.O365Integration.O365DomainStatus

## NOTES

## RELATED LINKS

[Set-O365Domain](./Set-O365Domain.md)

[Remove-O365Domain](./Remove-O365Domain.md)

