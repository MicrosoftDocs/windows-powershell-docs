---
external help file: IpamServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 1BEB28C1-6E04-4C8E-91C1-10EB8AFBB42B
manager: dansimp
---

# Get-IpamConfiguration

## SYNOPSIS
Gets the configuration for the computer running the IP Address Management (IPAM) server.

## SYNTAX

```
Get-IpamConfiguration
```

## DESCRIPTION
The **Get-IpamConfiguration** cmdlet gets the configuration for the computer running the IP Address Management (IPAM) server, including the software version number and the TCP port number over which the computer running the IPAM Remote Server Administration Tools (RSAT) client connects and communicates with the computer running the IPAM server.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-IpamServerConfiguration
Version : 1.3 
Port    : 48885
```

This example gets the configuration for the computer running the IPAM server, including the software version number and the TCP port number over which the computer running the IPAM RSAT client connects and communicates with the computer running the IPAM server.

## PARAMETERS

## INPUTS

### None

## OUTPUTS

### Microsoft.Windows.Ipam.Commands.IpamConfiguration
This object contains an IPAM configuration.

## NOTES

## RELATED LINKS

[Set-IpamConfiguration](./Set-IpamConfiguration.md)

