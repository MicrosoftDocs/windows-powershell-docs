---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
Download Help Link: http://go.microsoft.com
external help file: Microsoft.SystemInsights.Management.PowerShell.dll-help.xml
Locale: en-US
Module Name: SystemInsights
ms.date: 06/18/2018
online version: https://learn.microsoft.com/powershell/module/systeminsights/get-insightscapabilityresult?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InsightsCapabilityResult
---

# Get-InsightsCapabilityResult

## SYNOPSIS
Gets the most recent prediction or the last 30 predictions from the specified capabilities.

## SYNTAX

```
Get-InsightsCapabilityResult [-Name] <String> [-History] [[-ComputerName] <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-InsightsCapabilityResult** cmdlet gets the most recent prediction or the last 30 predictions from the specified capabilities.

>[!IMPORTANT]
>Some information relates to prereleased product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

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
PS C:\> Get-InsightsCapabilityResult -Name "CPU capacity forecasting" -History
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

### Microsoft.SystemInsights.Management.PowerShell.Capability

You can use the pipeline operator to pass a capability object to the *Name* parameter.


## OUTPUTS

### Microsoft.SystemInsights.Management.PowerShell.CapabilityResult

The cmdlet returns one or more objects that represent the specified capability results.

## RELATED LINKS
[Get-InsightsCapability](get-insightscapability.md)

[Invoke-InsightsCapability](invoke-insightscapability.md)
