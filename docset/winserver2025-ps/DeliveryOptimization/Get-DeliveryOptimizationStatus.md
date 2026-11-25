---
external help file: DeliveryOptimizationStatus.psm1-help.xml
Module Name: DeliveryOptimization
ms.date: 11/02/2026
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/get-deliveryoptimizationstatus?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DeliveryOptimizationStatus
---

# Get-DeliveryOptimizationStatus

## SYNOPSIS

Gets the current status of Delivery Optimization jobs and their peers.

## SYNTAX

```
Get-DeliveryOptimizationStatus [-PeerInfo] [-AsObject] [-SelectPeerCount <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Get-DeliveryOptimizationStatus` cmdlet returns a real-time snapshot of Delivery Optimization
jobs on the local device. Each job includes its file ID, size, download status, priority, transfer
totals, download sources, cache expiration, and pinning status.

Use **PeerInfo** to get per-file peer details, such as IP addresses, peer types, connection
status, and bytes sent and received. Use **AsObject** with **PeerInfo** to group those details
in an object for each file.

## EXAMPLES

### Example 1: Get current job status

```powershell
Get-DeliveryOptimizationStatus
```

This command returns status objects for current Delivery Optimization jobs.

### Example 2: Get peer details as objects

```powershell
Get-DeliveryOptimizationStatus -PeerInfo -AsObject -SelectPeerCount 10
```

This command returns a file-level object for each job, with up to 10 peers in its **PeersInfo**
property. Peers are sorted by bytes received, from highest to lowest.

## PARAMETERS

### -AsObject

Returns a file-level object containing **FileId** and **PeersInfo** properties instead of
writing file IDs and peer objects separately. Use this parameter with **PeerInfo**.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PeerInfo

Returns peer information for each file instead of the default job statistics. Peer information
includes IP address, peer type, connection status, and transfer statistics.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -SelectPeerCount

Specifies the maximum number of peers to return for each file when you use **PeerInfo**.
Peers are sorted by bytes received, from highest to lowest. Specify a positive integer.
The default is `5`.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

You can't pipe objects to this cmdlet.

## OUTPUTS

### DOSwarmStats

Job statistics returned when you don't specify **PeerInfo**.

### DOFilePeerInfo

A file ID and its associated peer objects, returned with **PeerInfo** and **AsObject**.

### System.String

A file ID written before its peer details when you use **PeerInfo** without **AsObject**.

### DOPeerInfo

Individual peer details returned with **PeerInfo** when you don't specify **AsObject**.

## NOTES

Use the **FileId** property when managing cached files with `Set-DeliveryOptimizationStatus`
or `Delete-DeliveryOptimizationCache`.

## RELATED LINKS

[Get-DeliveryOptimizationPerfSnap](Get-DeliveryOptimizationPerfSnap.md)

[Set-DeliveryOptimizationStatus](Set-DeliveryOptimizationStatus.md)

[Delete-DeliveryOptimizationCache](Delete-DeliveryOptimizationCache.md)

[Monitor Delivery Optimization](https://learn.microsoft.com/windows/deployment/do/waas-delivery-optimization-monitor)
