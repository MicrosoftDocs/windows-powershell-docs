---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Get-MbamCMIntegration
---

# Get-MbamCMIntegration

## SYNOPSIS
Gets the configuration of the MBAM Microsoft Endpoint Configuration Manager Integration feature.

## SYNTAX

```
Get-MbamCMIntegration [<CommonParameters>]
```

## DESCRIPTION
The **Get-MbamCMIntegration** cmdlet gets the configuration of the Microsoft BitLocker Administration and Monitoring (MBAM) Microsoft Endpoint Configuration Manager Integration feature.

## EXAMPLES

### Example 1: Get the configuration of the Microsoft Endpoint Configuration Manager Integration feature
```
PS C:\> Get-MbamCMIntegration
Name        : Configuration Manager Integration
Enabled     : False
Description : This feature will integrate MBAM with a Microsoft Endpoint Configuration Manager server.
```

This command gets the configuration of the MBAM Microsoft Endpoint Configuration Manager Integration feature in the local server.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.MBAM.Server.Commands.CMIntegrationConfiguration

## NOTES

## RELATED LINKS

[Disable-MbamCMIntegration](disable-mbamcmintegration.md)

[Enable-MbamCMIntegration](enable-mbamcmintegration.md)

[Test-MbamCMIntegration](test-mbamcmintegration.md)


