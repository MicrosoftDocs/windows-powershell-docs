---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wsscomputer?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WssComputer

## SYNOPSIS
Gets device information objects for the computers in a network.

## SYNTAX

```
Get-WssComputer
```

## DESCRIPTION
The **Get-WssComputer** cmdlet gets the device information objects for the computers in a network.
A **DeviceInfo** object contains the properties for a computer.
The cmdlet gets **DeviceInfo** objects for servers, clients, and archived clients.
An archived client is a backup of a computer that is no longer part of the network.

## EXAMPLES

### Example 1: Get properties for computers in a network
```
PS C:\> Get-WssComputer
```

This command gets the **DeviceInfo** objects for the computers in the network.

## PARAMETERS

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.Common.Devices.DeviceInfo
A **DeviceInfo** object contains all the properties for a computer in the network.

## NOTES

## RELATED LINKS

[Remove-WssComputer](./Remove-WssComputer.md)

