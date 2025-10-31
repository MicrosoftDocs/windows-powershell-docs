---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clustersharedvolumestate?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterSharedVolumeState
---

# Get-ClusterSharedVolumeState

## SYNOPSIS
Gets the state of Cluster Shared Volumes in a cluster.

## SYNTAX

```
Get-ClusterSharedVolumeState [-Node <StringCollection>] [[-Name] <StringCollection>] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ClusterSharedVolumeState** cmdlet gets the state of Cluster Shared Volumes in a cluster.

## EXAMPLES

### 1:
```
PS C:\> Get-ClusterSharedVolumeState
Name                : Cluster Disk X 
VolumeName          : \\?\Volume{2297f079-53c2-41e9-94d1-483d61ea94d7}\
Node                : ClusterNode1
State               : Direct

VolumeFriendlyName  : Volume1
RedirectedIOReason  : NotRedirected

Name                : Cluster Disk Y 
VolumeName          : \\?\Volume{0312ef48-74c7-4a4d-946e-4bb4a397ad1f}\
Node                : ClusterNode2
State               : File System Redirected

VolumeFriendlyName  : Volume2
RedirectedIOReason  : UserRequest

Name                : Cluster Disk Z 
VolumeName          : \\?\Volume{c4689cef-83e3-4f47-9eaf-161a9e31c5a0}\
Node                : ClusterNode3
State               : Block Redirected
VolumeFriendlyName  : Volume3
RedirectedIOReason  : NoDiskConnectivity
```

This command gets the state of Cluster Shared Volumes on the local cluster.

## PARAMETERS

### -Cluster

Specifies the name of the cluster on which to run this cmdlet. If you specify a period (`.`) or
don't specify this parameter, the cmdlet runs on the local cluster.

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

### -InputObject

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this
cmdlet.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Specifies the names, as a collection of strings, of the Cluster Shared Volumes for which to get
state information.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node

Specifies the names, as a collection of strings, of the cluster nodes for which to get the state of
Cluster Shared Volumes.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

### Microsoft.FailoverClusters.PowerShell.ClusterNode

### Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-ClusterSharedVolume](./Get-ClusterSharedVolume.md)
