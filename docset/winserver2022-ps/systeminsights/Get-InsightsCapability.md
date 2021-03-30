---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
Module Name: systeminsights
Download Help Link: http://go.microsoft.com
Locale: en-US
title: Get-InsightsCapability
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
ms.assetid: 38D3C463-40AC-4E35-944F-5AC57EEB45A7
schema: 2.0.0
---

# Get-InsightsCapability

## SYNOPSIS
Gets the specified capability, or all available capabilities if left unspecified.

## SYNTAX

```
Get-InsightsCapability [[-Name] <String>] [[-ComputerName] <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-InsightsCapability** cmdlet gets the specified capability, or all available capabilities if left unspecified.

>[!IMPORTANT]
>Some information relates to prereleased product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-InsightsCapability
```

This example gets all capabilities. 

### Example 2
```powershell
PS C:\> Get-InsightsCapability -Name "CPU capacity forecasting" 
```

This example gets the **CPU capacity forecasting** capability.

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
Specifies a capability using a capability name. If unspecified, all capabilities will be returned.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N

Required: False
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

### Microsoft.SystemInsights.Management.PowerShell.Capability

The cmdlet returns one or more objects that represent the specified capabilities.

## RELATED LINKS
[Get-InsightsCapabilitySchedule](get-insightscapabilityschedule.md)

[Get-InsightsCapabilityAction](get-insightscapabilityaction.md)

[Get-InsightsCapabilityResult](get-insightscapabilityresult.md)
