---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
Module Name: systeminsights
Download Help Link: http://go.microsoft.com
Locale: en-US
title: Enable-InsightsCapabilitySchedule
ms.reviewer:
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: xxx
keywords: powershell, cmdlet
author: andreabarr
manager: elizapo
ms.date: 6/18/18
ms.topic: reference
ms.prod: w10
ms.technology: powershell-windows
ms.assetid: 38D4C234-40FB-4E35-943F-5AC56EEB55A7
schema: 2.0.0
---

# Enable-InsightsCapabilitySchedule

## SYNOPSIS
Enables periodic predictions for the specified capabilities.

## SYNTAX

```
Enable-InsightsCapabilitySchedule [-Name] <String> [[-ComputerName] <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Enable-InsightsCapabilitySchedule** cmdlet enables periodic predictions for the specified capabilities.

>[!IMPORTANT]
>Some information relates to prereleased product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## EXAMPLES

### Example 1
```powershell
PS C:\> Enable-InsightsCapabilitySchedule -Name "CPU capacity forecasting"
```

This example enables periodic predictions for the **CPU capacity forecasting** capability.

## PARAMETERS

### -ComputerName
Specifies a fully qualified domain name (FQDN). If not specified, uses the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Credential
Specifies the credential for accessing the computer specified by the -ComputerName parameter.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a capability using a capability name. 

```yaml
Type: String
Parameter Sets: (All)
Aliases: N

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.SystemInsights.Management.PowerShell.Capability

You can use the pipeline operator to pass a capability object to the *Name* parameter.

## OUTPUTS

### None

## RELATED LINKS
[Get-InsightsCapability](get-insightscapability.md)

[Disable-InsightsCapabilitySchedule](disable-insightscapabilityschedule.md)

[Set-InsightsCapabilitySchedule](set-insightscapabilityschedule.md)
