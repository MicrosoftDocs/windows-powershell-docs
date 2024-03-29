---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
Download Help Link: http://go.microsoft.com
external help file: Microsoft.SystemInsights.Management.PowerShell.dll-help.xml
Locale: en-US
Module Name: SystemInsights
ms.date: 06/18/2018
online version: https://learn.microsoft.com/powershell/module/systeminsights/get-insightscapabilityschedule?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InsightsCapabilitySchedule
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

