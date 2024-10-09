---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
Download Help Link: https://aka.ms/winsvr-2025-pshelp
Help Version: 5.0.0.1
Locale: en-US
Module Guid: b55fd86f-287c-470c-9ac6-647dc76c15ce
Module Name: SystemInsights
ms.date: 06/18/2018
title: SystemInsights
---

# SystemInsights Module

## Description
The System Insights module contains the PowerShell cmdlets for [System Insights](https://aka.ms/SystemInsights), a predictive analytics feature for Windows Server 2019.

>[!IMPORTANT]
>Some information relates to prereleased product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## systeminsights Cmdlets
### [Add-InsightsCapability](Add-InsightsCapability.md)
The **Add-InsightsCapability** cmdlet dynamically adds a new capability using the specified capability name and capability library.

### [Disable-InsightsCapability](Disable-InsightsCapability.md)
The **Disable-InsightsCapability** cmdlet deactivates a capability, which stops data collection for that capability and prevents the capability from being invoked.

### [Disable-InsightsCapabilitySchedule](Disable-InsightsCapabilitySchedule.md)
The **Disable-InsightsCapabilitySchedule** cmdlet disables periodic predictions for the specified capabilities.

### [Enable-InsightsCapability](Enable-InsightsCapability.md)
The **Enable-InsightsCapability** cmdlet activates a capability, which starts all data collection for that capability, allows the capability to be invoked, and enables users to set custom configuration information.

### [Enable-InsightsCapabilitySchedule](Enable-InsightsCapabilitySchedule.md)
The **Enable-InsightsCapabilitySchedule** cmdlet enables periodic predictions for the specified capabilities.

### [Get-InsightsCapability](Get-InsightsCapability.md)
The **Get-InsightsCapability** cmdlet gets the specified capability, or all available capabilities if left unspecified.

### [Get-InsightsCapabilityAction](Get-InsightsCapabilityAction.md)
The **Get-InsightsCapabilityAction** cmdlet gets the actions for the specified capabilities. 

### [Get-InsightsCapabilityResult](Get-InsightsCapabilityResult.md)
The **Get-InsightsCapabilityResult** cmdlet gets the most recent prediction or the last 30 predictions from the specified capabilities.

### [Get-InsightsCapabilitySchedule](Get-InsightsCapabilitySchedule.md)
The **Get-InsightsCapabilitySchedule** cmdlet gets the schedule for the specified capabilities.

### [Invoke-InsightsCapability](Invoke-InsightsCapability.md)
The **Invoke-InsightsCapability** cmdlet invokes the specified capability.

### [Remove-InsightsCapability](Remove-InsightsCapability.md)
The **Remove-InsightsCapability** cmdlet permanently removes a capability from System Insights. 

### [Remove-InsightsCapabilityAction](Remove-InsightsCapabilityAction.md)
The **Remove-InsightsCapabilityAction** cmdlet removes the action(s) associated with a capability.

### [Set-InsightsCapabilityAction](Set-InsightsCapabilityAction.md)
The **Set-InsightsCapabilityAction** cmdlet sets a remediation action that is tied to a prediction result.

### [Set-InsightsCapabilitySchedule](Set-InsightsCapabilitySchedule.md)
The **Set-InsightsCapabilitySchedule** cmdlet sets a prediction schedule for the specified capabilities.

### [Update-InsightsCapability](Update-InsightsCapability.md)
The **Update-InsightsCapability** cmdlet updates an existing System Insights capability. Updating a capability will preserve all of the custom configuration information associated with a capability.

