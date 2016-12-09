---
author: jamiejdt
description: 
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: 
ms.assetid: 44A98F6A-9820-4F24-BF66-F292B7012EC2
ms.date: 2016-12-05
ms.devlang: powershell
ms.service: MDOP
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-MbamCMIntegration
---

# Get-MbamCMIntegration

## SYNOPSIS
Gets the configuration of the MBAM System Center Configuration Manager Integration feature.

## SYNTAX

```
Get-MbamCMIntegration [<CommonParameters>]
```

## DESCRIPTION
The **Get-MbamCMIntegration** cmdlet gets the configuration of the Microsoft BitLocker Administration and Monitoring (MBAM) System Center Configuration Manager Integration feature.

## EXAMPLES

### Example 1: Get the configuration of the System Center Configuration Manager Integration feature
```
PS C:\> Get-MbamCMIntegration
Name        : Configuration Manager Integration
Enabled     : False
Description : This feature will integrate MBAM with a Microsoft System Center Configuration Manager server.
```

This command gets the configuration of the MBAM System Center Configuration Manager Integration feature in the local server.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.MBAM.Server.Commands.CMIntegrationConfiguration

## NOTES

## RELATED LINKS

[Disable-MbamCMIntegration](disable-mbamcmintegration.md)

[Enable-MbamCMIntegration](enable-mbamcmintegration.md)

[Test-MbamCMIntegration](test-mbamcmintegration.md)


