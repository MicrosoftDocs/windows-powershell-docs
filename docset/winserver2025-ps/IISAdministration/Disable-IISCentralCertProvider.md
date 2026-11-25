---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/disable-iiscentralcertprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-IISCentralCertProvider
---

# Disable-IISCentralCertProvider

## SYNOPSIS
Disables the IIS central certificate store.

## SYNTAX

```
Disable-IISCentralCertProvider [<CommonParameters>]
```

## DESCRIPTION
The **Disable-IISCentralCertProvider** cmdlet disables the IIS central certificate store.
The central certificate store allows you to store all your IIS certificates in a centralized location (such as a file share); IIS servers then retrieve certificate from this centralized location.
That means that you only have to install certificates in one location; there is no need to install the same certificate on each and every IIS server.
If you disable the central certificate store then you will need to install certificates on all of your servers.

If the certificate store has been disabled you can re-enable it at any time by running the **Enable-IISCentralCertProvider** cmdlet.

## EXAMPLES

### Example 1
```
PS C:\> Disable-IISCentralCertProvider
```

This command disables the central certificate store.
Note that no parameters are required when calling **Disable-IISCentralCertProvider**.
Note, too that you will not be asked to confirm whether you want to disable the central store.
Instead, the store will automatically be disabled when you run this command.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Clear-IISCentralCertProvider](./Clear-IISCentralCertProvider.md)

[Enable-IISCentralCertProvider](./Enable-IISCentralCertProvider.md)

[Get-IISCentralCertProvider](./Get-IISCentralCertProvider.md)

[Set-IISCentralCertProvider](./Set-IISCentralCertProvider.md)

[Set-IISCentralCertProviderCredential](./Set-IISCentralCertProviderCredential.md)

