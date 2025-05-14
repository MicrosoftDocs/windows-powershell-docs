---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
Download Help Link: http://go.microsoft.com
external help file: Microsoft.SystemInsights.Management.PowerShell.dll-help.xml
Locale: en-US
Module Name: SystemInsights
ms.date: 06/18/2018
online version: https://learn.microsoft.com/powershell/module/systeminsights/set-insightscapabilityschedule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-InsightsCapabilitySchedule
---

# Set-InsightsCapabilitySchedule

## SYNOPSIS
Sets a prediction schedule for the specified capabilities.

## SYNTAX

### Daily with interval
```
Set-InsightsCapabilitySchedule [-Name] <String> [-Daily] [[-DaysInterval] <UInt16>] [[-At] <DateTime>]
 [[-ComputerName] <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Daily with days of week
```
Set-InsightsCapabilitySchedule [-Name] <String> [-Daily] [[-DaysOfWeek] <DayOfWeek[]>] [[-At] <DateTime>]
 [[-ComputerName] <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Minute
```
Set-InsightsCapabilitySchedule [-Name] <String> [[-DaysOfWeek] <DayOfWeek[]>] [-Minute]
 [[-MinutesInterval] <UInt16>] [[-ComputerName] <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Hourly
```
Set-InsightsCapabilitySchedule [-Name] <String> [[-DaysOfWeek] <DayOfWeek[]>] [-Hourly]
 [[-HoursInterval] <UInt16>] [[-ComputerName] <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Default
```
Set-InsightsCapabilitySchedule [-Name] <String> [-DefaultSchedule] [[-ComputerName] <String>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-InsightsCapabilitySchedule** cmdlet sets a prediction schedule for the specified capabilities.

>[!IMPORTANT]
>Some information relates to prereleased product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## EXAMPLES

### Example 1
```powershell
PS C:\> Set-InsightsCapabilitySchedule -Name "CPU capacity forecasting" -Daily -DaysOfWeek Monday, Tuesday, Wednesday, Thursday, Friday -At 03:00
```

This example sets a daily schedule for the **CPU capacity forecasting** capability, which runs every weekday at 3am.

### Example 2
```powershell
PS C:\> Set-InsightsCapabilitySchedule -Name "CPU capacity forecasting" -Daily -DaysInterval 2
```

This example sets a daily schedule for the **CPU capacity forecasting** capability, which runs every 2 days.

### Example 3
```powershell
PS C:\> Set-InsightsCapabilitySchedule -Name "CPU capacity forecasting" -Hourly -HoursInterval 4 -DaysOfWeek Tuesday, Friday
```

This example sets a hourly schedule for the **CPU capacity forecasting** capability, which runs every 4 hours on Tuesday and Friday.

### Example 4
```powershell
PS C:\> Set-InsightsCapabilitySchedule -Name "CPU Capacity Forecasting" -DefaultSchedule
```

This example restores the default schedule for the **CPU capacity forecasting** capability.


## PARAMETERS

### -At
Specifies the time of day to get a prediction. This parameter can only be specified for daily predictions.

```yaml
Type: DateTime
Parameter Sets: Daily with Interval, Daily with Days
Aliases: A

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Daily
Uses days as the scheduled time interval.

```yaml
Type: SwitchParameter
Parameter Sets: Daily with Interval, Daily with Days
Aliases: D

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysInterval
Specifies the interval between days in the schedule. An interval of 1 produces a daily schedule. An interval of 2 runs the capability every other day.

```yaml
Type: UInt16
Parameter Sets: Daily with Interval
Aliases: DI

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfWeek
Specifies the days of the week to run the capability.

```yaml
Type: DayOfWeek[]
Parameter Sets: Daily with Days, Minute, Hourly
Aliases: DOW
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultSchedule
Restores the default schedule of the capability.

```yaml
Type: SwitchParameter
Parameter Sets: Default
Aliases: DS

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Hourly
Uses hours as the scheduled time interval.

```yaml
Type: SwitchParameter
Parameter Sets: Hourly
Aliases: H

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HoursInterval
Specifies the interval between hours in the schedule. An interval of 1 produces an hourly schedule. An interval of 2 produces a prediction every 2 hours.

```yaml
Type: UInt16
Parameter Sets: Hourly
Aliases: HI

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Minute
Uses minutes as the scheduled time interval.

```yaml
Type: SwitchParameter
Parameter Sets: Minute
Aliases: M

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinutesInterval
Specifies the interval between minutes in the schedule. An interval of 5 produces a prediction every 5 minutes. An interval of 10 produces a prediction every 10 minutes. The default value is 30, and it is not recommended to specify low values of this parameter, as it may negatively impact performance.

```yaml
Type: UInt16
Parameter Sets: Minute
Aliases: MI

Required: False
Position: 3
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

## RELATED LINKS
[Get-InsightsCapability](get-insightscapability.md)

[Get-InsightsCapabilitySchedule](get-insightscapabilityschedule.md)

[Enable-InsightsCapabilitySchedule](enable-insightscapabilityschedule.md)

[Disable-InsightsCapabilitySchedule](disable-insightscapabilityschedule.md)
