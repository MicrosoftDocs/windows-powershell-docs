---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
Download Help Link: http://go.microsoft.com
external help file: Microsoft.SystemInsights.Management.PowerShell.dll-help.xml
Locale: en-US
Module Name: SystemInsights
ms.date: 06/18/2018
online version: https://learn.microsoft.com/powershell/module/systeminsights/invoke-insightscapability?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-InsightsCapability
---


# Invoke-InsightsCapability

## SYNOPSIS
Invokes the specified capability.

## SYNTAX

```
Invoke-InsightsCapability [-Name] <String> [[-ComputerName] <String>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-InsightsCapability** cmdlet invokes the specified capability.

>[!IMPORTANT]
>Some information relates to prereleased product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## EXAMPLES

### Example 1
```powershell
PS C:\> Invoke-InsightsCapability -Name "CPU capacity forecasting"
```

This example invokes the **CPU capacity forecasting** capability.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Specifies the credential for accessing the computer specified by the -ComputerName parameter.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

## NOTES
The **Invoke-InsightsCapability** won't return until the specified capabilities have finished running.

## RELATED LINKS
[Get-InsightsCapability](get-insightscapability.md)

[Get-InsightsCapabilityResult](get-insightscapabilityresult.md)

[Get-InsightsCapabilitySchedule](get-insightscapabilityschedule.md)

[Set-InsightsCapabilitySchedule](set-insightscapabilityschedule.md)
