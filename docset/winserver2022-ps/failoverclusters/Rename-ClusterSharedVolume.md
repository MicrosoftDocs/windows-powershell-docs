---
description: Rename-ClusterSharedVolume
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 07/26/2022
online version: https://docs.microsoft.com/powershell/module/failoverclusters/rename-clustersharedvolume?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-ClusterSharedVolume
---

# Rename-ClusterSharedVolume

## SYNOPSIS
Renames a cluster shared volume.

## SYNTAX

```
Rename-ClusterSharedVolume [-Name] <String> [[-VolumeName] <String>] -NewVolumeName <String>
 [-NewVolumeGuid <String>] [<CommonParameters>]
```

## DESCRIPTION
The `Rename-ClusterSharedVolume` cmdlet renames a specified cluster shared volume.

## EXAMPLES

### Example 1
```powershell
Rename-ClusterSharedVolume -Name "CSV01" -NewVolumeName "CONTOSOCSV01"
```

This command renames the cluster shared volume from CSV01 to CONTOSOCSV01.

## PARAMETERS

### -Name
Specify the name of the cluster shared volume to rename.

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

### -NewVolumeGuid
Specify the new volume GUID of the cluster shared volume.

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

### -NewVolumeName
Specify the new volume name of the cluster shared volume.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeName
{{ Fill VolumeName Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
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

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Add-ClusterSharedVolume](./Add-ClusterSharedVolume.md)

[Get-ClusterSharedVolume](Get-ClusterSharedVolume.md)

[Move-ClusterSharedVolume](./Move-ClusterSharedVolume.md)

[Remove-ClusterSharedVolume](./Remove-ClusterSharedVolume.md)
