---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
Module Name: systeminsights
Download Help Link: http://go.microsoft.com
Locale: en-US
title: Get-InsightsCapabilitySchedule
ms.reviewer:
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file:
keywords: powershell, cmdlet
author: Kateyanne
manager: elizapo
ms.date: 06/18/2018
ms.topic: reference
ms.prod: w10
ms.technology: 
ms.assetid: 38D3C772-40AB-4E35-993F-5AC58EEB55A7
schema: 2.0.0
---

# Get-InsightsCapabilitySchedule

## SYNOPSIS
Gets the schedule for the specified capabilities.

## SYNTAX

```
Get-InsightsCapabilitySchedule [-Name] <String> [[-ComputerName] <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-InsightsCapabilitySchedule** cmdlet gets the schedule for the specified capabilities.

>[!IMPORTANT]
>Some information relates to prereleased product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-InsightsCapabilitySchedule -Name "CPU capacity forecasting"
```

This example gets the schedule for the **CPU capacity forecasting** capability.

### Example 2
```powershell
PS C:\> Get-InsightsCapability | Get-InsightsCapabilitySchedule 
```

This example uses the **Get-InsightsCapability** cmdlet and the pipeline operator to get the schedule for all available capabilities. 

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

### Microsoft.SystemInsights.Management.PowerShell.CapabilitySchedule

The cmdlet returns one or more objects that represent the specified capability schedules.

## RELATED LINKS
[Get-InsightsCapability](get-insightscapability.md)

[Set-InsightsCapabilitySchedule](set-insightscapabilityschedule.md)

[Enable-InsightsCapabilitySchedule](enable-insightscapabilityschedule.md)

[Disable-InsightsCapabilitySchedule](disable-insightscapabilityschedule.md)

