---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: jgerend
Module Name: systeminsights
Download Help Link: http://go.microsoft.com
Locale: en-US
title: Get-InsightsCapabilityResult
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
keywords: powershell, cmdlet
author: JasonGerend
manager: elizapo
ms.date: 6/18/18
ms.topic: reference
ms.prod: w10
ms.technology: powershell-windows
ms.assetid: 38D3C589-40AB-4E35-843F-5AC57EEB65A7
schema: 2.0.0
---

# Get-InsightsCapabilityResult

>[!IMPORTANT]
>Some information relates to prereleased product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## SYNOPSIS
Gets the most recent prediction or the last 30 predictions from the specified capabilities.

## SYNTAX

```
Get-InsightsCapabilityResult [-Name] <String> [-History] [[-ComputerName] <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-InsightsCapabilityResult** cmdlet gets the most recent prediction or the last 30 predictions from the specified capabilities.

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-InsightsCapabilityResult -Name "CPU capacity forecasting"
```

This example gets the most recent result for the **CPU capacity forecasting** capability.

### Example 2
```powershell
PS C:\> Get-InsightsCapability | Get-InsightsCapabilityResult 
```

This example uses the **Get-InsightsCapability** and the pipeline operator to get the most recent result for all capabilities.

### Example 3
```powershell
PS C:\> Get-InsightsCapability -Name "CPU capacity forecasting" -History
```

This example uses the **History** parameter to get the most last 30 results for the **CPU capacity forecasting** capability.

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

### -History
Retrieves the most recent 30 predictions for the specified capability. 

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: H

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

### System.String
**Microsoft.SystemInsights.Management.PowerShell.Capability**

You can use the pipeline operator to pass a capability object to the *Name* parameter.

### System.Object
**Microsoft.SystemInsights.Management.PowerShell.CapabilityResult**

The cmdlet returns one or more objects that represent the specified capbility results.

## OUTPUTS
**None**

## RELATED LINKS
[Get-InsightsCapability](get-insightscapability.md)<br>
[Invoke-InsightsCapability](invoke-insightscapability.md)