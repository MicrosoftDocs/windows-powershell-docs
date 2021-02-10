---
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
online version: 
schema: 2.0.0
title: Repair-ClusterSharedVolume
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 7DDE6081-9975-47F0-8E56-93E636261F6C
---

# Repair-ClusterSharedVolume

## SYNOPSIS
Runs repair tools on a Cluster Shared Volume locally on a cluster node.

## SYNTAX

### ChkDsk (Default)
```
Repair-ClusterSharedVolume [-VolumeName] <String> [-ChkDsk] [-Parameters <String>] [<CommonParameters>]
```

### Defrag
```
Repair-ClusterSharedVolume [-VolumeName] <String> [-Defrag] [-Parameters <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Repair-ClusterSharedVolume** cmdlet runs repair tools on a Cluster Shared Volume locally on a cluster node.

This cmdlet runs **chkdsk.exe** or **defrag.exe** on a Cluster Shared Volume.
It will turn maintenance on for the volume, move the cluster resource to the node running this cmdlet, run the tool, and then turn maintenance off for the volume.
This cmdlet has to run locally on one of the cluster nodes.
To run remotely, use Windows PowerShell® remoting.

## EXAMPLES

### Example 1
```
PS C:\>Repair-ClusterSharedVolume -VolumeName C:\ClusterStorage\Volume1 -Defrag
```

This example runs defrag.exe on Cluster Shared Volume located at C:\ClusterStorage\Volume1.

### Example 2
```
PS C:\>Repair-ClusterSharedVolume -VolumeName C:\ClusterStorage\Volume1 -ChkDsk -Parameters "/F"
```

This example runs chkdsk.exe on Cluster Shared Volume located at C:\ClusterStorage\Volume1 and passes the /F parameter to chkdsk.exe.

## PARAMETERS

### -ChkDsk
Specifies that **chkdsk.exe** is run on the volume.
Any parameters specified in the **Parameters** parameter will be passed through to **chkdsk.exe**.

```yaml
Type: SwitchParameter
Parameter Sets: ChkDsk
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Defrag
Specifies that **defrag.exe** is run on the volume.
Any parameters specified in the **Parameters** parameter will be passed through to **defrag.exe**.

```yaml
Type: SwitchParameter
Parameter Sets: Defrag
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameters
Specifies one or more parameters to pass through to the tool.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeName
Specifies the name of the volume on which to run the tool.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-ClusterSharedVolume](./Get-ClusterSharedVolume.md)

[Resume-ClusterResource](./Resume-ClusterResource.md)

[Suspend-ClusterResource](./Suspend-ClusterResource.md)

