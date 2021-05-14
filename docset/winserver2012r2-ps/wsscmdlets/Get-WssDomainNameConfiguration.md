---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssdomainnameconfiguration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssDomainNameConfiguration
---

# Get-WssDomainNameConfiguration

## SYNOPSIS
Gets the domain name configuration of the Windows Server Essentials computer.

## SYNTAX

```
Get-WssDomainNameConfiguration [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssDomainNameConfiguration** cmdlet gets the domain name configuration of the Windows Server Essentials computer.
This cmdlet returns Windows Server Essentials domain configuration settings, the name of the domain provider, the certificate status, and the expiration date of the certificate.

## EXAMPLES

### Example 1: Get the domain name configuration of the Windows Server
```
PS C:\> Get-WssDomainNameConfiguration
```

This command gets the domain name configuration of Windows Server Essentials.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.RemoteAccess.Domains.DomainNameConfiguration
This cmdlet generates the currently active domain name configuration object.

## NOTES

## RELATED LINKS

[Set-WssDomainNameConfiguration](./Set-WssDomainNameConfiguration.md)

