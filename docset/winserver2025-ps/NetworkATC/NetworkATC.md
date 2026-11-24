---
Download Help Link: https://aka.ms/winsvr-2025-pshelp
Help Version: 5.1.0.2025
Locale: en-US
Module Guid: 74bd14cc-e0b8-42f9-b940-0ad938bb852b
Module Name: NetworkATC
ms.date: 03/14/2025
title: NetworkATC module
---

# NetworkATC Module

## Description

The NetworkATC modules are part of a toolset provided for automating and
managing network configurations in a software-defined networking (SDN)
environment. These modules enable administrators to automate the setup,
configuration, and monitoring of network traffic policies and routes, ensuring
optimal performance and resource allocation.

## NetworkATC Cmdlets

### [Add-NetIntent](Add-NetIntent.md)

Configures the network host using intent-based tags for adapters.

### [Copy-NetIntent](Copy-NetIntent.md)

Moves or copies network intents across different hosts or clusters.

### [Get-AllNetIntents](Get-AllNetIntents.md)

Looks up all intent requests configurations available

### [Get-HUDSwitchlessMapping](Get-HUDSwitchlessMapping.md)

Retrieves the HUD switchless mapping configuration for the specified cluster.

### [Get-NetIntent](Get-NetIntent.md)

Gets the current set of intents configured on the node or cluster.

### [Get-NetIntentAllGoalStates](Get-NetIntentAllGoalStates.md)

Looks up all intent goal state configurations available

### [Get-NetIntentStatus](Get-NetIntentStatus.md)

Displays the consolidated status of all the intent configurations for a node or across multiple nodes in a cluster.

### [New-NetIntentAdapterPropertyOverrides](New-NetIntentAdapterPropertyOverrides.md)

Creates a new instance of network adapter property overrides which can be used to supply granular values to `Set-NetIntent`.

### [New-NetIntentAdapterRssOverrides](New-NetIntentAdapterRssOverrides.md)

Creates a new instance of RSS overrides which can be used to supply granular values to `Set-NetIntent`.

### [New-NetIntentGlobalClusterOverrides](New-NetIntentGlobalClusterOverrides.md)

Creates a new instance of cluster setting overrides which can be used to supply granular values to `Add-NetIntent`, `Get-NetIntent`, and `Set-NetIntent`.

### [New-NetIntentGlobalProxyOverrides](New-NetIntentGlobalProxyOverrides.md)

Creates a new instance for global proxy overrides.

### [New-NetIntentQoSPolicyOverrides](New-NetIntentQoSPolicyOverrides.md)

Creates a new instance of QoS policy overrides which can be used to supply granular values to `Set-NetIntent`.

### [New-NetIntentSiteOverrides](New-NetIntentSiteOverrides.md)

Creates a new instance of site configuration overrides which can be used to supply granular values to `Set-NetIntent`.

### [New-NetIntentStorageOverrides](New-NetIntentStorageOverrides.md)

Creates a new instance of network adapter storage overrides which can be used to supply granular values to `Set-NetIntent`.

### [New-NetIntentSwitchConfigurationOverrides](New-NetIntentSwitchConfigurationOverrides.md)

Creates a new instance of virtual switch configuration overrides which can be used to supply granular values to `Set-NetIntent`.

### [Remove-NetIntent](Remove-NetIntent.md)

Removes the requested network intent.

### [Set-NetIntent](Set-NetIntent.md)

Allows provisioning of override values for the given network intent.

### [Set-NetIntentRetryState](Set-NetIntentRetryState.md)

Changes the provisioning state of the goal state for an intent on a given host.

### [Set-NetIntentTracing](Set-NetIntentTracing.md)

Starts and stops Atc tracing sessions on the host

### [Start-NetworkAtc](Start-NetworkAtc.md)

Starts the Atc Service on all hosts for a cluster or a given single node.

### [Stop-NetworkAtc](Stop-NetworkAtc.md)

Stops the Atc Service on all hosts for a cluster or a given single node.

### [Update-NetIntentAdapter](Update-NetIntentAdapter.md)

Updates the network intent configuration for specified network adapters.

### [Update-NetIntentType](Update-NetIntentType.md)

Updates the configuration types of network intents for specified computers or clusters.

### [Update-NetworkATC](Update-NetworkATC.md)

Updates the Network ATC configuration settings.
